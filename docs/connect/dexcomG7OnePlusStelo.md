# Dexcom G7, ONE+, and Stelo

Use the `Dexcom G7/ONE+/Stelo` CGM choice for the integrated sensor and transmitter products in this family.

## Choose a connection mode

The first setup screen asks how xDrip4iOS should connect.

### Primary Mode

Use **Primary Mode** when xDrip4iOS should connect directly to the sensor and receive the readings itself.

Another app or device must not use the same Bluetooth channel. When using the default Mobile App channel, force-close the Dexcom app, CamAPS, or any other app already connected to the sensor before xDrip4iOS makes its first connection. See [Bluetooth Channel](#bluetooth-channel) if another app or device must remain connected on a different channel.

Primary Mode requires the four-digit pairing code from the current applicator. Keep the applicator until xDrip4iOS has connected successfully.

### Coexistence Mode

Use **Coexistence Mode** when the Dexcom app, CamAPS, or another compatible app controls the sensor connection.

The other app must remain running in the background and receiving current readings. Do not force-close it or remove its Bluetooth permission. If that app stops receiving readings, xDrip4iOS will also stop receiving them.

Start and manage the sensor in the other app. A pairing code is not required by xDrip4iOS in Coexistence Mode.

The selected G7 connection mode is kept for that saved device. To change it, remove the device from xDrip4iOS and add it again with the required mode. Removing it from xDrip4iOS does not stop the physical sensor.

## Connect in Primary Mode

1. In **Devices**, add a `Dexcom G7/ONE+/Stelo` CGM.
2. Select **Primary Mode**.
3. Enter the four-digit pairing code, select **Scan with Camera**, or select **Choose Photo**.
4. Check the code and any sensor information, then select **Continue**.
5. Leave the Bluetooth name empty and continue to the device screen.
6. Select **Scan** and keep the iPhone near the sensor.

Scanning the current applicator can also read the sensor serial number, manufacture date, and expiry date. Check the information before continuing.

If automatic search does not find the sensor, open the iPhone Bluetooth settings and find its name. Add the device again and enter all or part of that name. The name must begin with `DX` and can contain up to six characters.

The Bluetooth name is not the four-digit pairing code. xDrip4iOS recognises `DX01` identifiers as Stelo and `DX02` identifiers as ONE+. Other matching devices are shown as G7.

## Connect in Coexistence Mode

1. Start and pair the sensor in the app that will control it.
2. Confirm that the other app has a current reading.
3. In **Devices**, add a `Dexcom G7/ONE+/Stelo` CGM.
4. Select **Coexistence Mode**.
5. Leave the Bluetooth name empty and continue to the device screen.
6. Select **Scan** and keep the controlling app running in the background.

If CamAPS controls the sensor, see [Using xDrip4iOS with CamAPS](camAPS.md).

## Understanding the connection status

Dexcom G7-family sensors connect briefly when data is available and disconnect again between readings. After the first successful connection, the device shows a green **Waiting...** status with the elapsed waiting time. This is normal.

**Connected** can appear only briefly while data is being received. **Connecting** means that the sensor has not yet completed its first connection since it was activated in xDrip4iOS.

Do not disconnect or delete the sensor because it shows **Waiting...**. Check the latest reading time on **Home** if the wait becomes longer than the normal reading interval.

## Sensor start and status

xDrip4iOS reads the sensor start time, age, warm-up, and current status from the sensor. Adding a sensor that is already running does not restart it.

Manual start and stop controls are not shown for this family. A new sensor can show **Waiting for Sensor Start** before the session begins, followed by **Warming Up**. The **Sensor Management** screen and the data source section at the bottom of **Home** update when new session information is received.

In Coexistence Mode, start, replace, and stop the sensor in the app that controls it.

## Bluetooth Channel

Open the current sensor under **Devices**. **Bluetooth Channel** appears near the bottom of the device screen when **Primary Mode** is selected. It is also available while adding a sensor in Primary Mode.

The sensor provides separate Bluetooth channels for different types of app or device. In Primary Mode, xDrip4iOS connects directly through the selected channel. Another app or device using the same channel can prevent xDrip4iOS from connecting.

- `Slot 2: Mobile App (Default)` is the normal phone-app channel. This is the default and the validated direct xDrip4iOS connection.
- `Slot 1: Receiver or Pump` uses the channel normally assigned to a Dexcom receiver or compatible pump. Do not select it if a receiver or pump needs that channel.
- `Slot 3: Smart Watch` uses the channel intended for a directly connected smartwatch. Do not select it if a watch needs that channel.

Leave `Slot 2: Mobile App (Default)` selected for a normal xDrip4iOS setup. Select another channel only when the Mobile App channel must remain available for another app and you know that the selected receiver, pump, or smartwatch channel is free.

Changing the channel makes xDrip4iOS disconnect and reconnect using the new selection. A short interruption is normal. If readings do not resume, check that another app or device is not using the selected channel. Return to `Slot 2: Mobile App (Default)` if there is no specific reason to use another channel.

**Bluetooth Channel** is not shown in Coexistence Mode. The other app controls the sensor connection in that mode, so xDrip4iOS does not select or use a separate channel.

## Sensor information

When the current applicator was scanned, **Sensor Management** can show:

- Sensor Code
- Sensor Serial Number
- Manufacture Date
- Expiry Date.

The device screen can also show the sensor start date, firmware, version code, sensor status, Bluetooth signal strength, battery values, and **Read Success** when available.

## Calibration

G7-family sensors are factory calibrated. xDrip4iOS supports optional calibration submission for G7 and ONE+ in both **Primary Mode** and **Coexistence Mode**, subject to the sensor permitting it. In Coexistence Mode, the other app must authenticate the connection before xDrip4iOS can send the calibration.

After a calibration is entered, xDrip4iOS can show whether it is queued, sent, processing, completed, or rejected. A rejection can occur because of the value, time, a duplicate entry, or a limit reported by the sensor. Wait for the current calibration to finish before entering another one.

**Stelo:** Calibration has been observed to be accepted without changing the sensor readings. An accepted or completed status is therefore not proof that Stelo has applied the calibration. Do not rely on Stelo calibration in either connection mode.

Follow the Dexcom guidance for meter checks and calibrations. The availability of the control does not mean that calibration is required.

## Battery information

The device screen shows **Voltage A** and **Voltage B** after the sensor provides battery data. The coloured battery symbol uses limits intended for the G7 family and is different from the G6 transmitter assessment.

Select **Voltage B** to open **Battery History**. The chart begins after xDrip4iOS receives the first genuine battery reading. Gaps mean that no battery value was received during that period.

## 15-day G7 sensors

Some G7 products have a 15-day sensor life. When xDrip4iOS detects a compatible G7 identifier, the device screen can show **15 Day Sensor**.

Enable this only for a G7 sensor that is intended to run for 15 days. Stelo is recognised automatically. The setting changes how xDrip4iOS calculates and displays the expected sensor end. It does not extend the physical sensor session.

## Missing readings after a short gap

The sensor can send missing readings after it reconnects. xDrip4iOS waits briefly so that the current and missing readings can be stored in the correct order. A short delay after reconnection does not always mean that the connection has failed.

In Coexistence Mode, first confirm that the controlling app is still receiving current values. In Primary Mode, check the selected Bluetooth channel. Keep another Dexcom app disconnected unless it has been deliberately left on a different free channel.

## Using a heartbeat instead of direct CGM

`Dexcom G7/ONE+/Stelo` also appears in the **Follower Heartbeat** category. That option does not read glucose from the sensor. Use it only with Follower mode as described in [Follower Heartbeat devices](followerHeartbeat.md).
