# M5Stack and M5StickC

xDrip4iOS can send glucose display data to a compatible M5Stack or M5StickC running suitable firmware.

The M5 is a display device. It does not supply glucose readings.

## Prepare the device

Install compatible xDrip4iOS firmware from the project for your device. Its installation steps and USB drivers can change separately from xDrip4iOS.

- M5Stack firmware: [JohanDegraeve/M5_NightscoutMon](https://github.com/JohanDegraeve/M5_NightscoutMon)
- M5StickC firmware: [JohanDegraeve/M5_StickC_xdrip_iOS](https://github.com/JohanDegraeve/M5_StickC_xdrip_iOS)

Follow the release instructions in the selected firmware repository. Confirm the exact hardware model before flashing. Firmware for another M5 model can fail to start or display incorrectly.

## Add the display

Turn on the flashed device. In **Devices**, add an **M5Stack** device and select `M5Stack` or `M5StickC`. Select **Connect** and wait for the display to show the current xDrip4iOS reading.

## Configure the display

Open **Settings > Sharing and Services > M5Stack**. Available settings include:

- text colour
- a Bluetooth password.

In the **Devices** tab, select the configured device to find its display controls. Depending on the model, these can include background colour, rotation, brightness, and other device-specific options.

M5Stack can also show its battery level and provides a **Power Off** action. M5StickC has the common display controls but does not show every M5Stack-specific option.

Select the M5Stack battery value to open **Battery History** after the first genuine battery reading has been stored. Select **Signal Strength** to check the live Bluetooth connection.

Treat the Bluetooth password as a secret. Do not include it in screenshots or issue reports.

## If it does not connect

Confirm that the firmware supports an xDrip4iOS Bluetooth connection. Firmware made only for direct Nightscout access will not work for this connection. Restart the M5 device, keep it close to the iPhone, and confirm Bluetooth permission. Record the password and display settings before removing a saved configuration.

If the M5 connects but its glucose is old, first check the reading time on **Home**. The display cannot show a newer value than xDrip4iOS has received.
