# Dexcom G7, ONE+, and Stelo

Use the `Dexcom G7/ONE+/Stelo` CGM choice for the integrated sensor and transmitter products in this family.

## How this connection works

xDrip4iOS works alongside the official Dexcom app for this device family. The Dexcom app pairs with the sensor and controls its Bluetooth connection. xDrip4iOS then receives readings from the same active connection.

The Dexcom app must remain running in the background and receiving current readings. Do not force-close it or remove its Bluetooth permission. If the Dexcom app stops receiving readings, xDrip4iOS will also stop receiving them.

Start the sensor and complete any pairing steps in the official app before adding it to xDrip4iOS.

## Connect

Keep the Dexcom G7 app running in the background, connected to the sensor, and receiving current glucose values. xDrip4iOS receives this data through the connection maintained by the Dexcom app.

In **Devices**, add a `Dexcom G7/ONE+/Stelo` CGM. When the identifier screen opens, select **OK** without entering anything to search automatically. Keep the iPhone near the active sensor until xDrip4iOS identifies it and receives a reading.

If automatic search does not find the sensor, open the iPhone Bluetooth settings and find its name. Add the device again and enter all or part of that name. The name must begin with `DX` and can contain up to six characters.

The identifier is the Bluetooth identifier, not the four-digit pairing code. xDrip4iOS recognises `DX01` identifiers as Stelo and `DX02` identifiers as ONE+. Other matching devices are shown as G7.

## Understanding the connection status

Dexcom G7-family devices connect briefly when data is available and disconnect again between readings. After the first successful connection, the device shows a green **Waiting...** status with the elapsed waiting time. This is the normal state between readings.

**Connected** can appear only briefly while data is being received. **Connecting** means that the sensor has not yet completed its first connection since it was activated in xDrip4iOS.

Do not disconnect or delete the sensor because it shows **Waiting...**. Check that the official Dexcom app and **Home** both have a current reading if the waiting time becomes longer than the normal reading interval.

## Using a sensor session that is already running

xDrip4iOS reads the current sensor age, start time, and status from the sensor. Adding it does not start a new session or restart the warm-up.

Manual sensor start and stop controls are not available for this family. Start, replace, and stop the sensor through its official system. The **Sensor Management** screen and the data source section at the bottom of **Home** update after xDrip4iOS receives the session information.

## 15-day G7 sensors

Some G7 products have a 15-day sensor life. When xDrip4iOS detects a compatible G7 identifier, the device screen can show **15 Day Sensor**.

Enable this only for a G7 sensor that is intended to run for 15 days. Stelo is recognised automatically. The setting changes how xDrip4iOS calculates and displays the expected sensor end. It does not extend the physical sensor session.

## Device information

Open the configured sensor in **Devices** to see its Bluetooth name, connection time, sensor start date, sensor status, and **Read Success** information when available.

The sensor status comes from the Dexcom system. A connected Bluetooth state does not always mean that the sensor is ready to provide a glucose value. Check the sensor status and the reading time on **Home**.

## Missing readings after a short gap

The device can send missing readings after it reconnects. xDrip4iOS waits briefly so that the current and missing readings can be stored in the correct order. A short delay after reconnection does not always mean that the connection has failed.

If readings remain missing, first confirm that the official Dexcom app is still open in the background and receiving current values. Then check the configured sensor in **Devices**. Do not delete it as the first response to a short gap.

## Using a heartbeat instead of direct CGM

`Dexcom G7/ONE+/Stelo` also appears in the **Follower Heartbeat** category. That option does not read glucose from the device. Use it only with Follower mode as described in [Follower Heartbeat devices](followerHeartbeat.md).
