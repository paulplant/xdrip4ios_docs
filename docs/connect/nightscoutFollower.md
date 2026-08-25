# Nightscout follower

Nightscout follower mode downloads glucose entries from a Nightscout site.

## Configure

Under **Settings > Data Source**, select **Follower**, then select `Nightscout` from **Data Source**. Configure the complete URL and authentication under **Settings > Sharing and Services > Nightscout**. The URL must include `https://`.

Return to **Settings > Data Source** and select **Status**. The Nightscout screen shows the connection and server availability. Confirm that **Home** downloads a current reading.

Use **Alias** in the Profile section when a name should identify the person being followed.

Use a token with only the permissions that xDrip4iOS needs. Do not paste credentials into a public support message.

## AID Type

Under **Settings > Sharing and Services > Nightscout**, **AID Type** controls which additional treatment and AID information xDrip4iOS reads from Nightscout:

- **None** receives glucose and available treatments without an AID-specific status display.
- **Loop** reads status information produced by Loop.
- **OpenAPS/Trio/iAPS/AAPS** reads the OpenAPS-based information used by those systems.

Choose the system that writes the device status to the Nightscout site. This choice does not change how glucose readings are downloaded and it does not control the AID system.

The **AID Type** choice is available only when Nightscout is the selected source for pump and treatment information. If CareLink provides that information, Nightscout can still be used for glucose upload without also controlling the pump display.

## Reading history and gap filling

After a connection gap, xDrip4iOS requests readings from the last stored time. This includes frequent readings when the Nightscout site stores them more often than every five minutes.

When xDrip4iOS opens or returns to the foreground, it also checks recent Nightscout history for missing periods. It adds any missing readings that are still available on the Nightscout site without creating duplicates.

If **Pump & Treatments** is also set to use Nightscout, the same recovery can restore missing treatments, profile changes, and AID device status. This helps complete the Treatments tab, historical chart information, AID statistics, and reports after the app was unable to update for a period.

Gap filling repairs local history. It does not replay old glucose alarms as if the readings had arrived live.

## Background updates

Nightscout follower needs internet access and background opportunities from iOS. Start with **Normal** under **Settings > Data Source > Keep-alive**. Try **Aggressive** only if needed. Use **Continuous** only in extreme cases because it has the highest battery use.

Do not force-close xDrip4iOS. The Nightscout status can show a working server connection even when the newest entry on that server is old, so always check the glucose timestamp.

## If it does not connect

Confirm that the URL begins with `https://` and opens the intended Nightscout site. Check the token or API secret and any non-standard port. Use **Test Connection** under **Settings > Sharing and Services > Nightscout**.

The **Server** section on the follower status screen shows whether the site is reachable. A reachable site can still have no current glucose entries.

## Do not upload readings back to the same site

Do not upload readings to the Nightscout site from which xDrip4iOS downloads them. This can create duplicate readings and unnecessary traffic.
