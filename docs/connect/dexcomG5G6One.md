# Dexcom G6 and ONE

Use the `Dexcom G6/ONE` CGM choice for Dexcom G6, ONE, and compatible Anubis G6 transmitters.

!!! info "Dexcom G5 support"
    Dexcom G5 transmitters remain fully supported. They have been removed from the device names and most of this guide because they are now very obsolete. This keeps the setup choices clear for current users. Select `Dexcom G6/ONE` when adding a G5 transmitter.

## What you need

- the six-character transmitter ID
- an active sensor and transmitter
- Bluetooth permission
- Master mode in xDrip4iOS.

Find the transmitter ID on the transmitter box or in the source app. Do not enter the sensor code as the transmitter ID.

## Connect

In **Devices**, add a `Dexcom G6/ONE` CGM. Select the connection mode before entering the six-character transmitter ID.

- Select **Primary Mode** when xDrip4iOS should control the transmitter connection. Force-close any other app that connects to the transmitter or remove its Bluetooth permission.
- Select **Coexistence Mode** when the Dexcom app, CamAPS, or another compatible app controls the connection. Keep that app running in the background and receiving current readings.

Enter the transmitter ID, continue to the device screen, and select **Connect**. Keep the transmitter close for one reading cycle.

xDrip4iOS identifies the exact product from the transmitter ID when possible.

## Understanding the connection status

Dexcom transmitters connect briefly when a reading is available and disconnect again between readings. After the first successful connection, the device shows a green **Waiting...** status with the elapsed waiting time. This is the normal state between readings.

**Connected** can appear only briefly while data is being received. **Connecting** means that the transmitter has not yet completed its first connection since it was activated in xDrip4iOS.

Do not disconnect or delete the transmitter because it shows **Waiting...**. Check the latest glucose time on **Home** if the waiting time becomes longer than the normal reading interval.

## Sensor sessions

Open [Sensor Management](../use/sensor.md) from the toolbar at the top of **Home** to start or stop a sensor when the connected transmitter permits it. A G6-family start can request a sensor code. Enter the code printed for the sensor, scan the label with the camera, or choose a clear photo of the label. See [Scan a Dexcom G6 sensor label](../use/sensor.md#scan-a-dexcom-g6-sensor-label).

The scan fills in the four-digit code and can also save the label's lot number and sensor serial number. Check the decoded information before starting the sensor. Label scanning is optional and is not needed for a sensor session that is already running.

Some transmitters supply factory-calibrated readings and sensor dates. The available calibration controls depend on the transmitter.

### Connecting to a sensor session that is already running

You can add a transmitter after its sensor session has already been started in the Dexcom app, a receiver, or another compatible app. You do not need to start the sensor again in xDrip4iOS.

If xDrip4iOS asks for a sensor code, select **Use Without Code**. Check that **No code (0000)** is selected, then select **Continue** and confirm the warning. xDrip4iOS will read the current session from the transmitter and use its original start time. It will not send a new sensor start command, restart the warm-up, or change the existing session.

Keep the transmitter close and allow at least one reading cycle for the current session details to appear.

Do not scan the label or enter the printed code for this process. **Use Without Code** tells xDrip4iOS to check the session that is already stored in the transmitter.

The no-code choice does not replace the sensor code for a session that is already running. It is only used as a no-code start if the transmitter does not have an active session and you choose to start a new one.

If a Dexcom G6 sensor is started without a code, xDrip4iOS uses `0000`. This creates a no-code session and the transmitter will request calibrations after warm-up and periodically afterwards. Review the warning before selecting **Continue**.

## Using the Dexcom G6 with xDrip4iOS and other apps

A Dexcom G6 transmitter provides separate Bluetooth channels for a phone app and a Dexcom receiver or compatible pump. An app or device that is already using a channel can prevent another connection on that channel.

Two settings control how xDrip4iOS connects:

- **Coexistence Mode** allows another app to control the transmitter connection while xDrip4iOS receives the same readings.
- **Bluetooth Channel** selects which transmitter channel xDrip4iOS uses when it controls its own connection.

These settings are not interchangeable. **Bluetooth Channel** is disabled when **Coexistence Mode** is enabled because the other app controls the connection in that mode.

| Intended setup | Connection Mode | Bluetooth Channel |
| --- | --- | --- |
| xDrip4iOS is the only app connected to the transmitter | `Primary Mode` | `Slot 2: Mobile App (Default)` |
| The Dexcom app or CamAPS controls the connection | `Coexistence Mode` | Not used |
| xDrip4iOS connects independently while another phone app uses the Mobile App channel | `Primary Mode` | `Slot 1: Receiver or Pump` |
| An Anubis transmitter uses its extra third channel | `Primary Mode` | `Slot 3: Anubis Extra` |

### Primary Mode

Use **Primary Mode** when xDrip4iOS is the main app connected to the transmitter. xDrip4iOS controls the connection and receives readings directly.

The default **Mobile App** channel is the correct choice when xDrip4iOS is the only phone app connected directly. Another app using the same channel can compete with xDrip4iOS. One or both apps can then miss readings.

Force-close the other app or disable its Bluetooth permission unless you have deliberately configured **Coexistence Mode** or one of the experimental channels described below.

### Coexistence Mode

Use **Coexistence Mode** when another app must remain connected to the transmitter. This is normally the official Dexcom G6 app or CamAPS.

If CamAPS controls the transmitter, see [Using xDrip4iOS with CamAPS](camAPS.md) before changing its connection or Bluetooth permission.

The other app controls and authenticates the transmitter connection. xDrip4iOS receives the readings from that same connection. The other app must be connected to the same transmitter and receiving readings before this mode can work.

When adding the transmitter, select **Coexistence Mode** on the first setup screen. Confirm that the other app is connected to the same transmitter and has a current reading, then add the transmitter ID in xDrip4iOS.

Keep the other app running in the background. Do not swipe it away. If it stops receiving readings, loses Bluetooth permission, or is force-closed, xDrip4iOS will also stop receiving readings in **Coexistence Mode**.

The transmitter screen in **Devices** shows whether **Primary Mode** or **Coexistence Mode** is active. The G6 mode can be changed later. Changing it can interrupt readings until the next connection.

### Bluetooth Channel

Open the transmitter in **Devices**. **Bluetooth Channel** appears under **Developer Settings** for a compatible G6 or ONE transmitter.

The available choices are:

- `Slot 2: Mobile App (Default)` uses the normal phone-app channel. Leave this selected for a normal xDrip4iOS connection.
- `Slot 1: Receiver or Pump` makes xDrip4iOS use the channel normally reserved for a Dexcom receiver or compatible pump. This leaves the Mobile App channel available for another phone app. Do not select it if a receiver or pump needs that channel. xDrip4iOS can prevent that device from connecting.
- `Slot 3: Anubis Extra` is available only after xDrip4iOS has identified an Anubis transmitter. It leaves both standard channels available for other devices. Use it only for testing.

The two experimental choices display a warning before they are saved. A channel change is used the next time xDrip4iOS connects to the transmitter for a reading. It might not appear to change immediately.

If you do not have a specific reason to use another channel, select `Slot 2: Mobile App (Default)`. If readings stop after changing the channel, return to the default and wait for the next reading cycle.

## Battery information

The transmitter screen shows **Voltage A** and **Voltage B** after the transmitter provides battery data. The battery symbol uses limits intended for the G6 family.

Select **Voltage B** to open **Battery History**. The chart begins after the first genuine battery reading is stored. Select the available time range to review changes. Gaps mean that no battery value was received during that period.

The **Battery Low (G6)** alarm uses the G6 transmitter battery setting. This is separate from the G7 battery alarm.

## Transmitter dates

The G6 device screen groups the transmitter dates before the sensor and firmware information. **Transmitter Expires** has a green indicator when more than 10 days remain, yellow during the final 10 days, and red after the displayed date has passed.

Select **Transmitter Expires** to see the start date, expiry date, and estimated time remaining. The separate transmitter start row is hidden when this combined information is available.

## Anubis G6 transmitters

An Anubis transmitter is a community-modified Dexcom G6 transmitter. It is designed to remain usable for longer and supports functions that are not available on a standard G6 transmitter.

xDrip4iOS recognises an Anubis transmitter automatically. The transmitter screen in **Devices** shows **Anubis** with a green checkmark. Use the normal `Dexcom G6/ONE` CGM choice when connecting it.

Compatible Anubis transmitters and Dexcom G6 transmitters with an ID beginning with `8` can use [Direct to Watch](../display/directToWatch.md). The iPhone and Watch must use separate Bluetooth slots.

When an Anubis transmitter is detected, xDrip4iOS provides these extra features:

- The sensor warm-up time is shown as approximately 50 minutes instead of the standard two hours.
- The displayed transmitter life is calculated using 180 days instead of the standard 100 days.
- **Reset Transmitter** requests a transmitter reset on the next connection.
- **Last Reset Time** shows the last recorded reset.
- **Maximum Sensor Days** changes the sensor life reminder shown by xDrip4iOS. It can be set up to 60 days. Enter `0` to return to the default 10 days.
- **Bluetooth Channel** can offer `Slot 3: Anubis Extra`. This third channel is intended only for testing.

**Maximum Sensor Days** is only a visual reminder. It does not extend the sensor, keep a sensor session running, or stop the session when that number of days is reached.
