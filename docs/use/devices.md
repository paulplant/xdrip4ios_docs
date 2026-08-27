# Devices

The Devices tab manages CGM, Follower Heartbeat, and M5Stack devices.

## Device categories

- **CGM** devices provide direct glucose data in Master mode.
- **Follower Heartbeat** devices can help Follower mode check for readings in the background. They do not provide glucose.
- **M5Stack** devices receive glucose display data from xDrip4iOS.

The screen groups saved devices by category and shows their type, connection state, and ID or name.

## Add a device

Select the add button, select a category, and then select the device family. xDrip4iOS then shows the setup fields and actions for that device.

The **CGM** category lists the direct CGM families supported by xDrip4iOS. Before scanning for Libre 2, Dexcom, or Medtrum Nano Pump, the app shows the connection requirement for that system. Read and complete it before selecting **Scan**.

![The supported direct CGM device families in the Devices tab](../img/screenshots/source/devicesAddCgm.png)

## Device information

Select a configured device in the **Devices** tab. The page for that device always shows its connection and a connect or disconnect action. It can also include:

- name or alias
- transmitter ID
- battery information
- sensor details
- Dexcom G6 connection mode and Bluetooth channel
- the percentage of expected readings received
- Libre calibration options
- device-specific M5Stack controls
- a delete control.

An unavailable control can indicate that the device is connected, that another CGM is active, that an NFC scan is required, or that the selected family does not support the function.

Compatible EmaLink and OrangeLink devices added as a **Libre/Generic** Follower Heartbeat can show a battery level. The row is hidden when the device does not provide a supported battery value.

## Connection status and wait time

The device list and device information page distinguish these states:

- **Not Scanning** means that the device is not active.
- **Scanning** means that xDrip4iOS is searching for a new device.
- **Connecting** means that the device is active but has not yet completed its first connection.
- **Connected** means that Bluetooth is connected at that moment.
- **Waiting...** is the normal green state for a Dexcom device between readings after it has connected successfully.
- **Reconnecting** means that a continuously connected device has unexpectedly disconnected and xDrip4iOS is trying to restore it.

**Scanning**, **Connecting**, **Waiting...**, and **Reconnecting** show a clock and the elapsed time. For a Dexcom device, the **Waiting...** timer normally restarts after each brief connection. Check the glucose reading time if the wait becomes longer than the normal reading interval.

The connection timer was proposed by Dana Lewis and adapted for xDrip4iOS.

## Percentage of readings received

For a compatible CGM, select the device in the **Devices** tab and open **Read Success**. It shows the percentage and number of expected readings received during the last 24 hours. The hourly chart shows when the gaps occurred. Use it to distinguish an occasional gap from a repeated connection problem. The expected number is based on the normal reading interval observed for that transmitter.

## Delete a device

Deleting removes the device from xDrip4iOS. It does not stop the physical sensor or delete data from an online service.
