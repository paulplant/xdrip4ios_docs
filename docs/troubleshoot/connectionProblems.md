# No readings or disconnections

Use this checklist when the Home value is old or a direct CGM device is disconnected.

## Confirm the scope

Check whether the problem affects only xDrip4iOS or also the manufacturer's receiver or app. Check the physical sensor state before changing xDrip4iOS.

## Direct Bluetooth checklist

1. Confirm that xDrip4iOS is in Master mode.
2. Check the configured CGM in the **Devices** tab.
3. Confirm that Bluetooth is enabled and xDrip4iOS has permission.
4. Keep the iPhone near the transmitter for at least one normal reading interval.
5. Confirm that the transmitter is not at its connection limit.
6. Confirm that the companion app is running or disconnected as required by the selected CGM.
7. For Libre 2 direct, repeat NFC only if the device screen says that a scan is needed.
8. Check transmitter or relay battery when the device reports it.
9. Select the CGM in the **Devices** tab and open **Read Success**. Review the 24-hour percentage and hourly chart.

## Check how your CGM shares Bluetooth

Different CGM systems must be used with their official app in different ways.

### Dexcom G6 and ONE

Open the device in the **Devices** tab and check **Connection Mode**.

- **Primary** means xDrip4iOS uses the main transmitter connection. The Dexcom app must not also try to use that connection.
- **Coexistence** allows xDrip4iOS to receive readings while the Dexcom app uses the main connection. The Dexcom app must remain running in the background.

If both apps are required, use Coexistence. If xDrip4iOS is the only app receiving directly from the transmitter, use Primary. See [Dexcom G6 and ONE](../connect/dexcomG5G6One.md).

### Dexcom G7, ONE+, and Stelo

The official Dexcom app controls the sensor connection. It must remain running in the background and continue receiving readings. Start and pair the sensor in the Dexcom app first.

If the official app has stopped receiving readings, correct that connection before changing xDrip4iOS. See [Dexcom G7, ONE+, and Stelo](../connect/dexcomG7OnePlusStelo.md).

### Libre 2 and Libre 2 Plus EU

xDrip4iOS needs Bluetooth access, but Bluetooth permission for the Libre app must remain disabled after the NFC setup scan. Enabling it can allow the Libre app to take the connection.

Repeat the NFC scan only when the device screen asks for it. Repeated scans do not repair a normal Bluetooth gap. See [Libre 2 and Libre 2 Plus EU](../connect/libre2.md).

### Libre with MiaoMiao or Bubble

Check that the bridge is charged, firmly positioned over the sensor, and selected as the correct family in xDrip4iOS. The battery shown in **Devices** is the bridge battery, not the Libre sensor battery. See [Libre with MiaoMiao or Bubble](../connect/libreTransmitters.md).

### Medtrum Nano Pump

The EasyPatch app controls the Medtrum connection. It must remain running in the background and continue receiving readings before xDrip4iOS can receive them. Start by checking EasyPatch. See [Medtrum Nano Pump](../connect/medtrum.md).

## Status meanings

- **Not scanning** means no active scan is running. Select **Connect** if the device should be active.
- **Scanning** means xDrip4iOS is looking for the Bluetooth device.
- **Connecting** means the device is active but has not yet completed its first connection.
- **Connected** means the Bluetooth connection is active at that moment.
- **Waiting...** is the normal green state for a Dexcom device between its brief reading connections. The elapsed time shows how long it has been waiting for the next connection.
- **Reconnecting** means a continuously connected device was connected before and xDrip4iOS is trying to restore the connection.
- **NFC scan needed** applies to Libre 2 direct setup.
- **Unauthorized** means iOS Bluetooth permission is not available to the app.
- **Powered off** means iPhone Bluetooth is off.

For Dexcom, **Waiting...** alone is not an error. Check the glucose reading time. Continue with the connection checks only when the reading is older than expected.

## Missing readings after a short gap

Some devices send missing readings after they reconnect. Wait for the older readings to appear before changing the connection.

The current reading should return first. Backfilled readings can then appear in **Glucose Readings** and on the chart. Old readings recovered after a gap do not cause old glucose alarms to play again.

## A sensor session is already running

Adding an existing sensor session does not normally require starting it again.

- For Dexcom G6 and ONE, leave the sensor code field showing its placeholder and select **OK**. xDrip4iOS reads the session already stored in the transmitter.
- For Dexcom G7, ONE+, and Stelo, start and pair the sensor in the official Dexcom app. xDrip4iOS receives that running session through the official app connection.
- For Libre 2 and Libre 2 Plus EU, scan the running sensor when requested. xDrip4iOS uses its existing start time.

Do not stop a working sensor only to add it to xDrip4iOS.

## Do not start with deletion

Deleting the device removes its saved ID and settings. Delete and add it again only after the normal checks fail and you have recorded those details.

If the device repeatedly disconnects, include the **Read Success** percentage, the hours that show gaps, and the times of the disconnections in [Report a problem](reportingIssues.md).
