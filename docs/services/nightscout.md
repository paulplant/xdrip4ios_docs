# Nightscout

xDrip4iOS can upload glucose and related data to Nightscout, follow a Nightscout site, and display selected AID information downloaded from Nightscout.

## Configure the connection

Open **Settings > Sharing and Services > Nightscout** and enter:

- the complete site URL
- the API secret or access token required by the site
- a port only when the deployment requires a non-default port
- the follow type appropriate for the server.

Use **Test Connection** before enabling uploads. This row shows when the last successful connection occurred. Open the site from the settings screen to confirm that the URL is correct.

## AID Type

**AID Type** controls which additional treatment and device status information xDrip4iOS reads from Nightscout:

- **None** for glucose and available treatments without an AID-specific status display
- **Loop** for status written by Loop
- **OpenAPS/Trio/iAPS/AAPS** for compatible OpenAPS-based status.

This choice affects the pump, Looping, landscape chart, and report information that xDrip4iOS can interpret. It does not control insulin delivery.

The choice is hidden when another service, such as CareLink, is selected for pump and treatment information.

## Upload glucose

In Master mode, enable **Upload to Nightscout** under **Settings > Data Source** after direct readings work. In Follower mode, enable it only when sending the downloaded readings to a different Nightscout site.

Nightscout settings can also upload sensor start time and use an upload schedule. When sensor-start upload is enabled, xDrip4iOS can upload the start time from a direct sensor or a LibreLinkUp Follower when that service supplies it. **Advanced Settings** can store readings that arrive more often than the normal five-minute interval.

When **Use Upload Schedule** is enabled, open **Schedule** to select when uploads are active. Readings remain stored locally outside those periods.

## Authentication

Prefer a scoped access token when your Nightscout version supports one. Treat the API secret and tokens as passwords. Do not include them in screenshots, logs, or public issue reports.

## Avoid duplicate readings

Do not download readings from a Nightscout site and upload the same readings back to it. If duplicate readings appear, check which apps are uploading and compare their reading times and device names.

For follower setup, see [Nightscout follower](../connect/nightscoutFollower.md).

## Import Nightscout history

In **Settings**, scroll to **Data Management**, then select **Import Data > Nightscout** to import glucose readings, treatments, and Device Status. The Nightscout URL and authentication must already be configured.

Device Status provides historical AID information for PDF reports, the landscape charts, and historical Looping status on **Home**.

Select the data and import period, then keep xDrip4iOS open until the import finishes. Existing local data is kept and matching records are skipped. If the import is interrupted, return to the same screen and select **Resume Import**.

The available period cannot exceed the local retention period selected under **Data Management > Manage Data > Data Retention**.
