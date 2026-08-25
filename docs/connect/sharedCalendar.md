# Shared Calendar follower

Shared Calendar follower mode receives glucose readings through a shared calendar.

It works with all releases of the app, including xDrip4iOS and Zukka. The source and follower do not need to use the same release.

No Nightscout site or other online account is required. Both users need access to the same shared calendar through a shared calendar link. A shared iCloud calendar is recommended because it has been proven to be very reliable for this function.

## Before you configure it

- Calendar Share must be active on the source iPhone.
- The source user must share the selected calendar with the follower user.
- The follower user must accept the calendar invitation.
- The shared calendar must appear in Apple's Calendar app on the follower iPhone.

See [Calendar Share](../services/calendarShare.md) for the source iPhone setup.

## Configure the follower iPhone

1. Open **Settings > Data Source**.
2. Select **Follower**.
3. Select `Shared Calendar` from **Data Source**.
4. Select **Status** to open the Shared Calendar settings.
5. Select **Calendar To Use** and choose the calendar shared by the source user.
6. Allow Full Calendar access when requested.
7. Return to **Home** and wait for a current reading.

The alias entered on the source iPhone is used to identify the person being followed.

## Background updates

Shared Calendar needs a keep-alive method, like the other online follower modes. When **Shared Calendar** is selected while **Keep-alive** is Disabled, xDrip4iOS changes it to Normal.

Start with **Normal**. Try **Aggressive** if Normal does not work reliably enough. Use **Continuous** only in extreme cases when both Normal and Aggressive do not work well enough. Continuous has the highest battery use. You can also configure a **Heartbeat** device.

iOS and the selected calendar account decide when calendar changes are delivered, so an exact update time cannot be guaranteed.

Do not force-quit the app. Keep Background App Refresh enabled and allow internet access for calendar syncing.

## Status and recent history

The Shared Calendar settings show the connection status, last value, and timestamp. When the source includes history, they also show how many recent readings were received and the time of the first reading.

Historical readings are added only when they are missing on the follower iPhone. This can fill a short gap without creating duplicate readings.

## If readings do not appear

Confirm that:

- the source iPhone shows a current reading
- Calendar Share is active on the source iPhone
- both users can see the same shared calendar in Apple's Calendar app
- the correct calendar is selected on the follower iPhone
- Full Calendar access is enabled
- **Keep-alive** is not Disabled
- both iPhones have internet access.

Always check the reading time. Calendar syncing or iOS background limits can delay a value even when the status does not show an error.
