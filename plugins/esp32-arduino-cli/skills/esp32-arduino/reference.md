# Classic ESP32 reference

Validated scope: classic ESP32 DevKitC / WROOM-32, FQBN `esp32:esp32:esp32`. Do not assume these pin details apply to ESP32-S2/S3/C3 or other variants; consult the exact datasheet.

## Boot-strapping pins

| GPIO | Boot role | Practical caution |
|---|---|---|
| 0 | Boot mode select | LOW can enter UART download mode |
| 2 | Boot-mode strapping | Avoid forcing an invalid level during reset |
| 12 (MTDI) | Flash voltage selection | HIGH at reset can select 1.8 V flash timing on common modules |
| 15 (MTDO) | Boot log / strapping | External pull levels can affect boot behavior |

GPIO6–GPIO11 are normally wired to integrated SPI flash on WROOM-32 modules. Do not use them as ordinary GPIO.

## ADC and Wi-Fi

Classic ESP32 ADC2 channels conflict with Wi-Fi operation. When Wi-Fi is active, prefer ADC1 GPIO32–GPIO39 for analog measurements, subject to the exact board pinout.

## Input-only pins

GPIO34–GPIO39 are input-only and do not provide software-controlled internal pull-up or pull-down resistors.

## Common FQBN

Classic ESP32 DevKitC / WROOM-32 commonly uses `esp32:esp32:esp32`. Verify the board definition and selected options using the installed Espressif Arduino core rather than assuming every DevKit V1 clone is identical.
