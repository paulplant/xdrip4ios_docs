# Direct to Watch

Direct to Watch allows a supported Dexcom transmitter to send glucose readings directly to Apple Watch when the paired iPhone is not nearby.

This is different from the normal xDrip4iOS Watch app and complications. Those displays normally receive their data from the iPhone. Direct to Watch adds a separate Bluetooth connection between the CGM and Apple Watch.

## Supported transmitters

Direct to Watch is available for:

- Dexcom G6 transmitters with an ID beginning with `8`
- compatible Anubis G6 transmitters
- the Dexcom G7 family, including G7, ONE+, and Stelo.

The iPhone must be in Master mode and use the Dexcom device as its direct data source. For G6, **Algorithm Type** must show **Native algorithm**. An active sensor must already be running on the iPhone.

For the G7 family, xDrip4iOS must use **Primary Mode** and have the current four-digit pairing code. Direct to Watch is not available when the iPhone uses **Coexistence Mode**.

Update xDrip4iOS on both the iPhone and Apple Watch before starting.

## Bluetooth slots

The iPhone and Apple Watch need different Bluetooth slots. A slot cannot be shared by two devices.

- **Slot 1 · Medical device** is normally used by a receiver, pump, or another medical device.
- **Slot 2 · Mobile app** is normally used by the iPhone app.
- **Slot 3 · Watch** is available on the G7 family and is the recommended Watch slot.
- **Slot 3 · Anubis extra** is available on compatible Anubis transmitters and is the recommended Watch slot.

Standard G6 transmitters have only the medical-device and mobile-app slots. If the iPhone uses the mobile-app slot, the Watch can connect only through the medical-device slot.

!!! warning
    Do not assign the Watch to a slot used by a pump, receiver, another phone app, or another smartwatch. Adding the Watch can interrupt that device's glucose connection. Confirm the slot is unused before continuing.

## Add the Watch connection

1. On the iPhone, open **Devices** and select the active Dexcom device.
2. Select **Direct to Watch**.
3. Select an available Bluetooth slot.
4. Select **Add Watch connection** and confirm any slot warning.
5. Open xDrip4iOS on Apple Watch.
6. Scroll to **Direct to Watch** and accept the Bluetooth pairing request if it appears.

Allow up to five minutes for the first connection. Sensor start, stop, and calibration controls remain on the iPhone.

## Using Direct to Watch

The **Direct to Watch** screen on Apple Watch shows the CGM type, Bluetooth slot, connection status, and readings waiting to synchronise with the iPhone.

The Watch stores readings that it collects. When it can communicate with the iPhone again, it sends those readings back to xDrip4iOS. The app handles readings collected by both devices without creating duplicate glucose history.

Select **Collected Readings** to review the readings stored on the Watch. Use **Pause Collection** when the Watch should temporarily stop connecting. Collection can also be paused from the iPhone device screen.

Triple-tap a glucose view in the Watch app to pause or resume collection quickly.

## Watch alerts

Direct to Watch provides independent switches for:

- **Urgent Low**
- **Low**
- **Missed Readings**.

The glucose thresholds follow the active iPhone alarm schedules. Watch glucose alerts are used only while Watch collection is running and the Watch has not communicated with the iPhone for more than 60 seconds. The Missed Readings alert is shown when the Watch has not received a reading for more than 20 minutes.

These settings do not replace the normal iPhone alarms. Check both devices after changing an alarm schedule.

## Background collection

watchOS controls Bluetooth background operation. Test Direct to Watch on your own Watch before relying on it while away from the iPhone. Compare the reading time and confirm that new readings continue while the Watch app is not visible.

Direct to Watch does not guarantee continuous readings or alarms. Keep the safety methods recommended for your CGM system.

## If the Watch does not receive readings

Open **Direct to Watch** on Apple Watch and check its status. Confirm that:

- the iPhone still has the correct active sensor
- the iPhone and Watch use different Bluetooth slots
- the G7 family is in Primary Mode and has the current pairing code
- the xDrip4iOS Watch app is installed
- Watch collection is not paused.

Use **Reset connection** on Apple Watch if the saved pairing must be cleared and created again. On the iPhone, **Testing and Logs** can temporarily pause iPhone Bluetooth collection, request Watch logs, and share the received log for support.

Do not leave iPhone Bluetooth collection paused after testing.
