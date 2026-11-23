---
name: esp32-arduino-dev
description: Build, validate, compile, flash, and debug firmware for classic ESP32 DevKit V1 boards using Arduino IDE and Arduino CLI. Use for ESP32 GPIO, sensors, Wi-Fi, Bluetooth, peripherals, libraries, compile errors, upload errors, and serial diagnostics.
---

# ESP32 DevKit V1 + Arduino IDE Engineering Workflow

## Mission

Produce firmware that is technically justified, reproducible, compilable, and safe to test on real hardware. Do not guess hardware details, fabricate test results, or claim that firmware works because the code looks plausible.

Target baseline: classic ESP32 (Xtensa LX6) DevKit V1 / ESP32-WROOM-32 using the Arduino-ESP32 core. DevKit V1 boards are sold in different layouts and with different USB-UART chips. Confirm the actual module, pinout, flash size, and port before relying on board-specific assumptions.

## Mandatory first step: establish facts

Before writing or changing firmware, identify:

1. Exact board/module marking (for example ESP32-WROOM-32), DevKit pin-count/layout, and USB-UART bridge if visible.
2. Arduino IDE version and installed esp32 by Espressif Systems core version.
3. Selected board profile in Arduino IDE, upload speed, flash frequency, flash mode, partition scheme, and PSRAM setting if relevant.
4. Serial port and operating system.
5. Exact task, expected inputs/outputs, voltage levels, connected modules, wiring, and power source.
6. Existing sketch structure and libraries already used.

Ask only for missing facts that materially affect the implementation. Never infer a sensor model, module voltage, pin mapping, or wiring from a vague description. If the user has a working sketch, inspect it before replacing or restructuring it.

## Hardware safety rules for classic ESP32

- Treat the exact board schematic and module datasheet as authoritative. Board silkscreen labels are not enough when a pin conflict is possible.
- GPIO6–GPIO11 are normally connected to SPI flash on classic ESP32 modules: do not assign them to external peripherals.
- GPIO34–GPIO39 are input-only and do not provide software-controlled internal pull-up/pull-down resistors.
- GPIO0, GPIO2, GPIO5, GPIO12, and GPIO15 are strapping pins. Avoid using them for circuits that can force an invalid level during reset/boot. GPIO12 deserves particular caution because its reset level affects flash supply configuration on common modules.
- GPIO1/GPIO3 are commonly used for UART0 programming and serial logs. Do not repurpose them if USB serial upload or Serial Monitor is required.
- ADC2 channels conflict with Wi-Fi use on the classic ESP32. Prefer ADC1 pins for analog measurements when Wi-Fi is active.
- ESP32 GPIO is 3.3 V logic and is not 5 V tolerant. Never connect a 5 V signal directly to a GPIO. Check module voltage and current requirements for every peripheral.
- Do not power motors, relays, LED strips, servos, or other high-current loads directly from GPIO. Use an appropriately rated driver/MOSFET/transistor and a suitable supply; establish a common ground where required.
- Never assume a GPIO can safely source or sink the required current. Check datasheet limits and design margin.
- Before suggesting a pin, state why it is suitable for the exact use case and list relevant conflicts.
- Do not recommend GPIO pin assignments until the connected peripherals and Wi-Fi/Bluetooth requirements are known.

## Firmware design rules

- Use the Arduino-ESP32 APIs that match the installed core version. Do not silently mix core 2.x and 3.x examples, especially LEDC/PWM APIs.
- Prefer non-blocking millis() state machines over long delay() calls when the device must also handle networking, sensors, buttons, or multiple tasks.
- Keep setup() and loop() readable. Separate drivers, application logic, configuration, and constants when complexity justifies it.
- Use explicit pin constants and meaningful names. Avoid unexplained magic numbers.
- Validate sensor reads and communication return codes. Handle timeouts, unavailable devices, reconnects, and invalid data.
- Avoid dynamic String concatenation in long-running or memory-constrained paths when it can cause heap fragmentation; use bounded buffers where appropriate.
- Do not add libraries unless required. Check the exact library name, maintainer, API, compatibility, and version before using it. Never invent library APIs.
- Keep credentials out of source control. Use a local ignored secrets header or another user-approved secret mechanism; never print Wi-Fi passwords or tokens in logs.
- Do not change board settings, partitions, flash mode, flash frequency, or erase flash to make an unexplained error disappear.

## Required project record

For each project, maintain a PROJECT_SPEC.md containing:
- Board/module and known hardware revision
- Arduino IDE and Arduino-ESP32 core versions
- Selected board FQBN and build options
- Wiring table: signal, ESP32 GPIO, peripheral pin, voltage, notes
- Libraries and pinned versions
- Functional requirements and acceptance tests
- Known limitations and unresolved questions

Maintain a BUILD_LOG.md with date, exact compile command/settings, tool/core versions, result, and relevant compiler output. Never replace a failed build log with a success claim.

## Required development loop

1. INSPECT: read the complete current sketch and relevant project files. Identify the smallest change that meets the requirement.
2. PLAN: describe the proposed behavior, files to change, GPIO allocation, libraries, and risks before a substantial rewrite.
3. CHECK HARDWARE: validate GPIO suitability and voltage/current compatibility. Flag any unresolved wiring question before proceeding.
4. IMPLEMENT: make the smallest coherent change. Preserve existing working behavior unless the user approves a redesign.
5. STATIC REVIEW: check declarations, types, includes, pin conflicts, blocking calls, memory use, error handling, and core-version API compatibility.
6. COMPILE: compile the exact project for the exact board FQBN using the installed Arduino-ESP32 core. Capture the complete result. Fix compile errors from the first real diagnostic, not by random edits.
7. REVIEW DIFF: summarize every changed file and verify no credentials, unrelated files, or accidental configuration changes were introduced.
8. HARDWARE TEST: only after the user approves, upload to the selected serial port. Then run Serial Monitor at the sketch's configured baud rate and verify observable behavior against acceptance tests.
9. REPORT: state separately what was statically checked, what compiled, what was uploaded, and what was physically tested. Mark anything not performed as NOT TESTED.

## Arduino CLI workflow (Windows)

Arduino IDE can remain the user's editor. Use Arduino CLI as a repeatable build and serial tool. First check availability:

    arduino-cli version
    arduino-cli core list
    arduino-cli board list

If the CLI is missing, explain the official installation route and ask before installing software. Do not silently change PATH or install tools.

Discover the exact board FQBN rather than guessing:

    arduino-cli board listall esp32

For the common generic classic ESP32 profile, esp32:esp32:esp32 may be available, but use the exact profile selected for the user's physical board and Arduino IDE configuration. Confirm it with:

    arduino-cli board details -b <FQBN>

Compile without uploading:

    arduino-cli compile --fqbn <FQBN> --warnings all <SKETCH_FOLDER>

Upload only after explicit user approval, after confirming the port and FQBN:

    arduino-cli upload --fqbn <FQBN> --port <COM_PORT> <SKETCH_FOLDER>

Monitor serial output only after confirming baud rate:

    arduino-cli monitor --port <COM_PORT> --config baudrate=<BAUD>

Do not combine compile and upload in a single unattended action. Compilation must pass first. Upload is a separate action requiring user approval.

If Arduino CLI is unavailable but Arduino IDE is installed, the user can compile with Verify in Arduino IDE. Ask for the full compiler output from the Output panel; do not claim a build passed without seeing its result.

## Debugging protocol

For every error:
1. Ask for or inspect the complete first error and surrounding compiler output, not just the final summary line.
2. Classify it: toolchain/core version, board/FQBN, missing library, C++ compile error, serial/USB driver, bootloader/upload, runtime crash, wiring/power, or peripheral protocol.
3. Identify the earliest causal diagnostic. Do not patch downstream errors before the first cause.
4. Propose one bounded change at a time when diagnosis is uncertain.
5. Recompile after each meaningful fix and preserve the output.
6. For runtime failures, capture boot log/reset reason, exact wiring, supply voltage, and reproducible steps.
7. Never claim a runtime fix based only on successful compilation.

## Explicit approval gates

Always ask before:
- Uploading/flashing firmware to a physical board
- Erasing flash, changing partition layout, or changing boot/flash configuration
- Installing/updating Arduino cores, libraries, drivers, Python packages, or other tools
- Changing system PATH, environment variables, or IDE settings
- Applying wiring changes that could damage the board or connected equipment

Read-only inspection and compilation of project files do not require a hardware write. Never execute destructive commands as a diagnostic shortcut.

## Definition of done

A task is DONE only when all applicable items are true:
- [ ] Hardware and board assumptions are confirmed or explicitly listed as assumptions.
- [ ] GPIO and voltage checks are complete.
- [ ] Code changes satisfy the stated acceptance criteria.
- [ ] Exact target configuration is recorded.
- [ ] Compilation succeeded and the relevant output is available.
- [ ] Changed files were reviewed.
- [ ] Upload and physical behavior were tested if the user approved hardware testing.
- [ ] Untested behavior and remaining risks are clearly disclosed.

If only compilation succeeded, report: COMPILED — NOT HARDWARE-TESTED.
If compilation did not succeed, report: NOT VERIFIED — BUILD FAILED.
Never report success without evidence.

## Reference sources

Prefer current primary documentation:
- Espressif Arduino-ESP32 documentation: https://docs.espressif.com/projects/arduino-esp32/en/latest/
- Espressif ESP32 datasheet: https://www.espressif.com/sites/default/files/documentation/esp32_datasheet_en.pdf
- Arduino CLI documentation: https://docs.arduino.cc/arduino-cli/
- Arduino CLI compile: https://docs.arduino.cc/arduino-cli/commands-reference/arduino-cli_compile
- Arduino CLI upload: https://docs.arduino.cc/arduino-cli/commands-reference/arduino-cli_upload

When a hardware fact is uncertain, consult the exact module datasheet and board schematic. Do not rely on a generic ESP32 pinout image for a board-specific electrical decision.
