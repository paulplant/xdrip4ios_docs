# Follower and service problems

Follower mode requires a working glucose source, internet access, and background opportunities from iOS.

## General checks

1. Confirm that xDrip4iOS is in Follower mode.
2. Confirm the selected **Data Source**.
3. Check that the source has a current reading. For Shared Calendar, check the source iPhone and the shared calendar.
4. Under **Settings > Data Source**, select **Status** and review the connection information.
5. Bring xDrip4iOS to the foreground and wait for a download.
6. Check credentials without sharing them.

The **Home** screen shows two separate pieces of information. The glucose timestamp shows when the reading was created. The data source section at the bottom of the screen shows whether xDrip4iOS can currently reach the selected source. Check both. A successful connection can still return an old reading.

## When readings update only with the app open

This normally means the source and account are working, but iOS is not giving xDrip4iOS enough background time.

Open **Settings > Data Source > Keep-alive**. Start with **Normal**. Use **Aggressive** if Normal is not reliable enough. **Continuous** has the highest battery use and should only be used in extreme cases when Normal and Aggressive do not work well enough.

**Heartbeat** requires a separate Bluetooth heartbeat device. The heartbeat does not provide glucose. It helps xDrip4iOS check the online source when the Bluetooth device communicates.

Also enable Background App Refresh and do not force close xDrip4iOS. No keep-alive method can guarantee an exact update time because iOS controls background operation.

## Nightscout

Confirm `https://`, the hostname, any required path, and token or API-secret permissions. Use the connection test. Do not follow and upload to the same site.

After a successful current download, xDrip4iOS checks recent history for gaps. Missing Nightscout readings can be added to the local chart without replaying alarms for those old readings. If a gap remains, confirm that the readings actually exist on the Nightscout site.

## LibreLinkUp

Confirm the correct standard or Russia service, email address, password, and account sharing. Correct invalid credentials before retrying because the app can pause repeated login attempts.

## Dexcom Share

Confirm that sharing works in the official Dexcom system and let xDrip4iOS detect the region. Share upload is intentionally disabled while Share follower is selected.

The person wearing the sensor must be actively sharing through Dexcom Share. A working local Dexcom sensor connection does not by itself make the reading available to followers.

## Medtrum EasyView

Confirm credentials and, for a caregiver account, select the intended patient. A patient selection resets if that connection is removed from the account.

## CareLink

Confirm the selected US or outside US region. Select **Status**, then complete **Log In** on Medtronic's page again if requested. The username and password saved in xDrip4iOS are optional and are used only to pre-fill that page.

Use a dedicated Care Partner account for xDrip4iOS. Signing in with the same follower account in another app or on another device can disconnect the existing session. Also confirm that the intended patient is selected.

If glucose is current but pump information is missing, check **Pump & Treatments** under **Settings > Data Source**. It must be set to **Automatic** or `CareLink`. Also confirm that the pump is communicating with the phone used by the CareLink system.

## Shared Calendar

Confirm that Calendar Share is active on the source iPhone and that both users can see the same calendar in Apple's Calendar app. On the follower iPhone, select that calendar, allow Full Calendar access, and make sure **Keep-alive** is not Disabled.

A shared iCloud calendar is recommended because it has been proven to be very reliable for this function. Another calendar can work if it is available through a shared link and updates correctly on both devices. The source and follower do not need to use the same xDrip4iOS or Zukka release.

## Old readings without an error

A follower source can provide an old reading without showing an error. Check the glucose timestamp. The source must provide a new reading before the follower can receive it.

Work backwards through the path:

1. Confirm that the source app or website has a current reading.
2. Confirm that the account, site, or shared calendar has received that reading.
3. Open xDrip4iOS and refresh the follower status where that option is available.
4. If the current reading then appears, review the background keep-alive settings.

Changing passwords, deleting the follower configuration, or reinstalling the app is not a useful first step when the source itself is old.
