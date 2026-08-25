# CareLink follower

CareLink follower mode receives glucose readings from a supported CareLink account.

## Before you configure it

- Confirm that the CareLink account can see current glucose readings.
- Know whether the account belongs to the United States service or the service used outside the United States.
- A Care Partner account must have access to the person you want to follow.
- Use a dedicated Care Partner account for xDrip4iOS. Using the same follower account in another app or on another device can disconnect the existing CareLink session.

## Configure

Under **Settings > Data Source**, select **Follower**, then select `CareLink` from **Data Source**. Select **Status** to open the CareLink settings.

In the **Account** section, select the correct region. The username and password fields are optional. If entered, they only pre-fill Medtronic's login page.

Select **Log In** and sign in on Medtronic's page. Complete any additional steps requested by Medtronic. If the account can see more than one patient, select the required person in the **Profile** section.

xDrip4iOS keeps the CareLink session active and renews it when possible. Medtronic can still require another login later.

The screen shows the connection state and any available account, patient, pump, sensor, and recent activity information. Return to **Home** and confirm that the reading time is current.

Use **Refresh** at the top of the CareLink screen to request a new check. Use **Log Out** when the account must be disconnected from xDrip4iOS.

The **Activity** section can show the last reading, last check, last session refresh, last therapy import, number of new treatments, and whether the service can be reached. Rows appear only when CareLink supplies that information.

## Pump and treatment information

CareLink can also provide pump and treatment information when it is available for the selected patient. Under **Settings > Data Source**, leave **Pump & Treatments** set to **Automatic** or select `CareLink`.

The pump section on **Home** can show available information such as active insulin, basal delivery, reservoir level, pump battery, and recent communication. Select it to open the full pump details.

The pump details can also show sensor time remaining and the limits reported by the pump. Coloured symbols beside the sensor and pump battery values help show when attention may be needed.

CareLink or MiniMed SmartGuard status can also appear on **Home** and in the Apple Watch app. SmartGuard is shown only when CareLink reports automated delivery activity. CareLink does not provide a changing carbohydrates on board value, so COB is not shown for this source.

Select **None** under **Pump & Treatments** if you only want CareLink glucose readings and do not want xDrip4iOS to import pump or treatment information.

## Automatic basal on the chart

When CareLink provides automatic basal deliveries, the **Therapy Display** section contains an **Automatic Basal** choice:

- **Basal Pulses** shows each automatic basal delivery as a short pulse on the main glucose chart.
- **Temp Basals** shows the equivalent U/hr rate between deliveries.

This changes how automatic basal is drawn. It does not change the stored insulin amount or control the pump.

## Statistics and reports

When CareLink supplies pump and treatment history, **Statistics > Trends** can show average total daily insulin and average carbohydrates. Total daily insulin includes recorded boluses and automatic basal deliveries.

The PDF report can also include a CareLink or MiniMed SmartGuard section when enough recent history is stored. It can show the pump, available SmartGuard activity, average total daily insulin, glucose, insulin on board, delivered insulin, and entered meal markers.

CareLink does not provide a changing COB value or the scheduled basal profile used by the report. The CareLink section therefore does not show a COB curve, Scheduled Basal Profile, or Temp Basal Delta. Entered carbohydrate amounts can still appear as meal markers.

These features are available when **Pump & Treatments** is set to **Automatic** or `CareLink`. They summarize information already received from CareLink. xDrip4iOS does not control the pump.

## Background updates

CareLink requires internet access and background opportunities from iOS. Select a suitable **Keep-alive** option under **Settings > Data Source**. Start with **Normal** and try **Aggressive** only if needed. Use **Continuous** only in extreme cases when Normal and Aggressive do not work well enough because it has the highest battery use. Do not force-quit xDrip4iOS.

## If CareLink does not connect

Confirm the selected region and complete the login on Medtronic's page again if requested. If saved login details are incorrect, change them in the **Account** section or correct them on the login page.

If the connection stops after the same Care Partner account is used in another app or on another device, use a separate follower account for xDrip4iOS and log in again. Also confirm that the intended patient is still available and selected.

If CareLink is connected but the reading is old, check the latest reading in CareLink itself. The pump can also stop updating when it is not communicating with the phone used by the CareLink system.

See [Follower and service problems](../troubleshoot/follower.md) for more checks.
