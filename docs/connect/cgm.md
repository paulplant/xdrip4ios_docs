# Add a direct CGM device

Use the **Devices** tab to add and manage a supported CGM device in Master mode.

## Before you add a device

Under **Settings > Glucose Display**, select the correct glucose unit. Under **Settings > Data Source**, select **Master** mode. Allow Bluetooth access when iOS asks. Keep the active sensor or transmitter near the iPhone.

Do not add the device from the iOS Bluetooth settings. xDrip4iOS scans and connects from inside the app.

## Add the device

In **Devices**, select the add button, **CGM**, and the device family. Complete the requested information or NFC scan, then select **Connect**. Wait for the first reading.

Only one CGM device can be active. If another CGM is present in **Devices**, disconnect or delete it before activating a replacement.

## Device-specific setup

- [Dexcom G6 and ONE](dexcomG5G6One.md)
- [Dexcom G7, ONE+, and Stelo](dexcomG7OnePlusStelo.md)
- [Libre 2 and Libre 2 Plus EU](libre2.md)
- [Libre with MiaoMiao or Bubble](libreTransmitters.md)
- [Medtrum Nano Pump](medtrum.md)
- [Using xDrip4iOS with CamAPS](camAPS.md)

## Connection status

In the **Devices** tab, select the configured CGM. Its information page shows the current connection status and how long the current wait has lasted.

**Connecting** is shown until the first successful connection after the device is activated. **Connected** means that the Bluetooth connection is active at that moment.

Dexcom devices connect briefly for each reading and normally disconnect between readings. After the first successful connection, they show a green **Waiting...** status until the next reading. This is normal and is not the same as a failed connection.

Other supported devices normally keep a continuous connection. **Reconnecting** means that one of these devices was connected before and xDrip4iOS is now trying to restore the connection.

The same page can show the transmitter ID, sensor information, battery information, and the percentage of expected readings received.

If the device does not connect, do not repeatedly press **Connect**. Wait for the current scan to finish, then follow [No readings or disconnections](../troubleshoot/connectionProblems.md).

## Remove or replace a device

In the **Devices** tab, select the device and then select the delete control. This removes the device from xDrip4iOS. It does not stop or remove the physical sensor.

!!! warning
    Do not delete an active device as a routine response to a short data gap. The saved details might be needed to reconnect.
