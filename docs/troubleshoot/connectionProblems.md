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
10. Open **Signal Strength** on the device screen and check the reception near the normal iPhone position.

For a continuously connected device, **Signal Strength** shows a live two-minute chart while the screen is open. For a Dexcom device, it shows the last measurement and its age because the transmitter disconnects between readings.

If **Battery History** is available, check whether the level or Dexcom Voltage B has been falling. Gaps in the chart mean that no battery value was received. They do not mean that the battery was empty.

## Check how your CGM shares Bluetooth

Different CGM systems must be used with their official app in different ways.

### Dexcom G6 and ONE

Open the device in the **Devices** tab and check **Coexistence Mode** and **Bluetooth Channel**.

- In **Coexistence Mode**, the Dexcom app or CamAPS controls the connection. That app must remain running in the background and receiving readings. **Bluetooth Channel** is disabled in this mode.
- In **Primary Mode**, xDrip4iOS controls its own connection. `Slot 2: Mobile App (Default)` is the normal channel. Another app using the same channel can cause missed readings.
- `Slot 1: Receiver or Pump` can leave the Mobile App channel available for another phone app. It can prevent a Dexcom receiver or compatible pump from connecting.
- `Slot 3: Anubis Extra` is available only for an identified Anubis transmitter and should be used only for testing.

If xDrip4iOS is the only app connected directly, select **Primary Mode** and `Slot 2: Mobile App (Default)`. If the Dexcom app or CamAPS controls the connection, select **Coexistence Mode**. Use another channel only when the setup specifically requires it. A channel change is used at the next transmitter connection. See [Dexcom G6 and ONE](../connect/dexcomG5G6One.md).

### Dexcom G7, ONE+, and Stelo

Open the sensor in **Devices** and check the selected connection mode.

- In **Primary Mode**, xDrip4iOS controls the connection. Other Dexcom apps must not use the same channel. Confirm that the pairing code came from the current applicator and leave `Slot 2: Mobile App (Default)` selected unless another channel is deliberately required.
- In **Coexistence Mode**, the Dexcom app, CamAPS, or another compatible app controls the connection. Keep it running in the background and confirm that it has a current reading.

See [Dexcom G7, ONE+, and Stelo](../connect/dexcomG7OnePlusStelo.md).

### Libre 2 and Libre 2 Plus EU

xDrip4iOS needs Bluetooth access, but Bluetooth permission for the Libre app must remain disabled after the NFC setup scan. Enabling it can allow the Libre app to take the connection.

Repeat the NFC scan only when the device screen asks for it. Repeated scans do not repair a normal Bluetooth gap. See [Libre 2 and Libre 2 Plus EU](../connect/libre2.md).

If CamAPS uses the Libre sensor, xDrip4iOS cannot receive direct readings from it at the same time. Do not change the CamAPS Bluetooth connection to troubleshoot xDrip4iOS. See [Using xDrip4iOS with CamAPS](../connect/camAPS.md).

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

- For Dexcom G6 and ONE, select **Use Without Code**, then select **Continue** and confirm the warning. xDrip4iOS reads the session already stored in the transmitter.
- For Dexcom G7, ONE+, and Stelo, xDrip4iOS reads the running session without restarting it. Primary Mode still requires the pairing code from the current applicator. In Coexistence Mode, manage the sensor in the controlling app.
- For Libre 2 and Libre 2 Plus EU, scan the running sensor when requested. xDrip4iOS uses its existing start time.

Do not stop a working sensor only to add it to xDrip4iOS.

## Do not start with deletion

Deleting the device removes its saved ID and settings. Delete and add it again only after the normal checks fail and you have recorded those details.

If the device repeatedly disconnects, include the **Read Success** percentage, the hours that show gaps, and the times of the disconnections in [How to ask for help](reportingIssues.md).
