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

In **Devices**, add a `Dexcom G6/ONE` CGM. Enter the six-character transmitter ID, select **Connect**, and keep the transmitter close for one reading cycle.

Before scanning, force-close any app that is already connected to the transmitter, such as the Dexcom app or CamAPS. The other app must not remain connected while xDrip4iOS makes its first connection or while xDrip4iOS is using the primary connection.

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

If xDrip4iOS asks for a sensor code, leave the field empty so that the `0000` placeholder remains, then select **OK**. xDrip4iOS will read the current session from the transmitter and use its original start time. It will not send a new sensor start command to the transmitter, restart the warm-up, or change the existing session.

Keep the transmitter close and allow at least one reading cycle for the current session details to appear.

Do not scan the label or replace the placeholder with the printed code for this process. The placeholder tells xDrip4iOS to check the session that is already stored in the transmitter.

The `0000` placeholder does not replace the sensor code for a session that is already running. It is only used as a no-code start if the transmitter does not have an active session and you choose to start a new one.

If a Dexcom G6 sensor is started without a code, xDrip4iOS uses `0000`. This creates a no-code session and the transmitter will request regular calibrations. Review the warning before selecting **Start Anyway**.

## Using the Dexcom G6 with xDrip4iOS and other apps

A Dexcom G6 transmitter provides separate Bluetooth channels for a phone app and a Dexcom receiver or compatible pump. An app or device that is already using a channel can prevent another connection on that channel.

Two settings control how xDrip4iOS connects:

- **Coexistence Mode** allows another app to control the transmitter connection while xDrip4iOS receives the same readings.
- **Bluetooth Channel** selects which transmitter channel xDrip4iOS uses when it controls its own connection.

These settings are not interchangeable. **Bluetooth Channel** is disabled when **Coexistence Mode** is enabled because the other app controls the connection in that mode.

| Intended setup | Coexistence Mode | Bluetooth Channel |
| --- | --- | --- |
| xDrip4iOS is the only app connected to the transmitter | Disabled | `Mobile App (Default)` |
| The Dexcom app or CamAPS controls the connection | Enabled | Disabled automatically |
| xDrip4iOS connects independently while another phone app uses the Mobile App channel | Disabled | `Receiver or Pump (Experimental)` |
| An Anubis transmitter uses its experimental third channel | Disabled | `Slot 3 (Anubis Experimental)` |

### Primary mode

Use **Primary mode** when xDrip4iOS is the main app connected to the transmitter. xDrip4iOS controls the connection and receives readings directly.

The default **Mobile App** channel is the correct choice when xDrip4iOS is the only phone app connected directly. Another app using the same channel can compete with xDrip4iOS. One or both apps can then miss readings.

Force-close the other app or disable its Bluetooth permission unless you have deliberately configured **Coexistence Mode** or one of the experimental channels described below.

### Coexistence Mode

Use **Coexistence Mode** when another app must remain connected to the transmitter. This is normally the official Dexcom G6 app or CamAPS.

If CamAPS controls the transmitter, see [Using xDrip4iOS with CamAPS](camAPS.md) before changing its connection or Bluetooth permission.

The other app controls and authenticates the transmitter connection. xDrip4iOS receives the readings from that same connection. The other app must be connected to the same transmitter and receiving readings before this mode can work.

When adding the transmitter to xDrip4iOS for the first time:

1. Force-close the other app.
2. Add the transmitter in xDrip4iOS and wait for it to connect.
3. Open the transmitter in **Devices** and enable **Coexistence Mode**.
4. Reopen the other app and confirm that it has a current reading.

Keep the other app running in the background. Do not swipe it away. If it stops receiving readings, loses Bluetooth permission, or is force-closed, xDrip4iOS will also stop receiving readings in **Coexistence Mode**.

If the other app is CamAPS, close it only while xDrip4iOS makes the initial connection. Reopen it immediately after enabling **Coexistence Mode**.

The transmitter screen in **Devices** shows whether **Primary mode** or **Coexistence Mode** is active. Changing the mode can interrupt the connection until the next reading cycle.

### Bluetooth Channel

Open the transmitter in **Devices**. **Bluetooth Channel** appears under **Developer Settings** for a compatible G6 or ONE transmitter.

The available choices are:

- `Mobile App (Default)` uses the normal phone-app channel. Leave this selected for a normal xDrip4iOS connection.
- `Receiver or Pump (Experimental)` makes xDrip4iOS use the channel normally reserved for a Dexcom receiver or compatible pump. This leaves the **Mobile App** channel available for another phone app. Do not select it if a receiver or pump needs that channel. xDrip4iOS can prevent that device from connecting.
- `Slot 3 (Anubis Experimental)` is available only after xDrip4iOS has identified an Anubis transmitter. It leaves both standard channels available for other devices. Use it only for testing.

The two experimental choices display a warning before they are saved. A channel change is used the next time xDrip4iOS connects to the transmitter for a reading. It might not appear to change immediately.

If you do not have a specific reason to use another channel, select `Mobile App (Default)`. If readings stop after changing the channel, return to the default and wait for the next reading cycle.

## Anubis G6 transmitters

An Anubis transmitter is a community-modified Dexcom G6 transmitter. It is designed to remain usable for longer and supports functions that are not available on a standard G6 transmitter.

xDrip4iOS recognises an Anubis transmitter automatically. The transmitter screen in **Devices** shows **Anubis** with a green checkmark. Use the normal `Dexcom G6/ONE` CGM choice when connecting it.

When an Anubis transmitter is detected, xDrip4iOS provides these extra features:

- The sensor warm-up time is shown as approximately 50 minutes instead of the standard two hours.
- The displayed transmitter life is calculated using 180 days instead of the standard 100 days.
- **Reset Transmitter** requests a transmitter reset on the next connection.
- **Last Reset Time** shows the last recorded reset.
- **Maximum Sensor Days** changes the sensor life reminder shown by xDrip4iOS. It can be set up to 60 days. Enter `0` to return to the default 10 days.
- **Bluetooth Channel** can offer `Slot 3 (Anubis Experimental)`. This third channel is intended only for testing.

**Maximum Sensor Days** is only a visual reminder. It does not extend the sensor, keep a sensor session running, or stop the session when that number of days is reached.
