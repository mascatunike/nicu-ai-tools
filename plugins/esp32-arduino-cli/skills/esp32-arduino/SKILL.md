---
name: esp32-arduino
version: 0.2.3
description: >
  Build, flash, and debug ESP32 .ino sketches with arduino-cli, including first-time
  environment setup. Trigger on build/upload/setup intent for an ESP32 project.
allowed-tools:
  - Bash(arduino-cli:*)
  - Read
  - Write
  - Edit
  - Glob
---

# esp32-arduino

Helps build, flash, and debug ESP32 sketches via `arduino-cli`. Tested against a classic ESP32 DevKitC / WROOM-32 board (FQBN `esp32:esp32:esp32`). Other variants (S2/S3/C3) differ in boot-strapping pins and peripherals; verify the exact board.

Never run OS-specific shell commands for board or port detection. Use `arduino-cli` so the workflow remains cross-platform.

**Show the literal `arduino-cli` command before running it and show its full output. Never summarize, truncate, or silently swallow output.**

## First step: project configuration

Look for `.esp32/config.json`. If present, read it. If absent, onboard by checking prerequisites, detecting the board and port, and asking only for preferences or facts that cannot be detected.

## Prerequisites and board detection

Run:
```sh
arduino-cli version
arduino-cli core list
arduino-cli board list
```

If `arduino-cli` is missing, explain the official installation route and stop. If the Espressif core is missing, show `arduino-cli core install esp32:esp32` and ask before installing it.

Use `arduino-cli board listall esp32` to discover board definitions. Default FQBN for classic ESP32 DevKitC/WROOM-32 is `esp32:esp32:esp32`, but verify against the physical board and IDE settings. If zero or multiple candidate ports are found, ask the user to choose.

## Compile, upload, monitor

Compile first and show all output:
```sh
arduino-cli compile --fqbn <FQBN> <SKETCH_FOLDER>
```

Never upload if compilation fails. Upload is a separate action and requires explicit user approval:
```sh
arduino-cli upload -p <PORT> --fqbn <FQBN> <SKETCH_FOLDER>
```

For live serial output, give the user the literal command:
```sh
arduino-cli monitor -p <PORT> -c baudrate=<BAUD>
```

Do not pretend a non-interactive shell has a live serial TTY. If the monitor cannot run interactively, ask the user to run it in their terminal and provide the output.

## Sketch and error handling

Arduino CLI expects the sketch folder and primary `.ino` filename to match (for example `Blink/Blink.ino`). Check this before compiling; ask before renaming.

For a missing header, identify the owning library and show the exact install command; ask before installing. For partition overflow, inspect the selected partition scheme and explain the trade-off; do not silently change flash layout. For other errors, start from the first causal compiler diagnostic and make one bounded correction at a time.

## ESP32-specific checks

- GPIO6–GPIO11 are normally connected to SPI flash on classic ESP32 modules; do not use them as general GPIO.
- GPIO34–GPIO39 are input-only and lack internal pull-up/pull-down.
- GPIO0, GPIO2, GPIO5, GPIO12 and GPIO15 are strapping pins; avoid external circuits that force invalid reset levels. GPIO12 is especially sensitive because it can affect flash voltage selection.
- GPIO1/GPIO3 are commonly used by UART0 for programming and serial logs.
- ADC2 readings conflict with Wi-Fi on classic ESP32; use ADC1 for analog reads while Wi-Fi is active.
- ESP32 GPIO is 3.3 V logic and is not 5 V tolerant. Verify voltage levels and current requirements for every peripheral.
- Use the exact module datasheet and board schematic when pinout details matter.

## Reporting rules

Report separately:
1. Static review completed.
2. Compilation result, including exact board/FQBN and core version.
3. Upload result, if user approved it.
4. Physical behavior actually observed through serial output or tests.

Mark unperformed steps as NOT TESTED. Never claim the firmware works solely because it compiles.

Keep a project-specific `.esp32/NOTES.md` append-only if the user opts in. Keep machine-specific port settings out of version control.
