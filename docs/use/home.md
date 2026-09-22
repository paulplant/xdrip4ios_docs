# Home

The Home tab shows the current glucose reading, charts, statistics, sensor information, and connection information.

## Current glucose

The large value is the latest glucose reading shown by xDrip4iOS. The surrounding information can include:

- the trend direction
- the change from a recent reading
- the reading age
- glucose-range colour
- pump information from CareLink or Nightscout when it is available
- open-source AID information when compatible Nightscout data is available
- connection information and, in Follower mode, the selected background update method.

Always check the reading age. A plausible value can still be unsafe to use when it is old.

## Main chart

The main chart shows recent readings and can also show treatments, calibrations, original readings, glucose-range lines, sensor noise, basal data, IOB, and COB when enabled.

- Drag horizontally to view earlier data.
- Double-tap the chart to return to the current time.
- Spread two fingers on the chart to zoom in to a shorter period.
- Pinch the chart inward to zoom out to a longer period.
- Select **Time Range** under **Quick Show/Hide > Chart** to choose the range directly.
- When the chart is moved into the past, the large value changes to the latest reading visible at the chart's end time. The value is shown as historical, not current.

The main chart periods are 3, 5, 8, 12, and 24 hours. A short message shows the selected period after a successful pinch.

[Clock Mode](screenLock.md) returns the chart to the current time and temporarily selects a range for its layout. It does not replace the saved chart period.

The mini chart provides a 1, 2, 3, or 7-day overview. Drag the highlighted time window to move the main chart through the stored history. Select the mini-chart period to choose a range, or double-tap the mini chart to move to the next period.

Open **Settings > General > Home Screen** and enable **IOB/COB Curves** to add available IOB and COB curves. The values can come from a connected AID source or can be estimated from recorded treatments. **Basal Position** selects whether pump basal data appears at the top or bottom of the chart. Basal injection markers remain with the treatment markers.

The **Therapy** switch controls all therapy content on Home and the landscape chart. This includes treatment markers, basal data, IOB and COB curves, pump information, and AID status. **Therapy Summary** separately controls the pump panel and therapy status area on Home.

## Statistics

When enabled, the statistics area shows low, in-range, and high percentages, average glucose, GMI, coefficient of variation, and a time-in-range chart. Use the period menu below the chart to view today, 1 day, 7 days, 30 days, or 90 days.

Statistics require enough valid readings. They are informational and depend on the glucose ranges configured in **Settings**.

Open **Statistics** for more detailed statistics, longer periods, trend charts, daily summaries, and PDF report generation.

## Landscape chart

Rotate the iPhone to landscape when rotation is enabled to compare one day of glucose readings with an Ambulatory Glucose Profile from recent history. **Show AGP chart data** selects 3, 7, 30, 60, or 90 previous days. Select **None** to hide the comparison profile.

The header shows the selected date, average glucose, and the range summary. Swipe left or right, or select the arrows at the sides, to change the day. Double-tap the middle of the chart or the date to return to today. Double-tap the range summary to switch between Time in Range and Time in Tight Range.

When **Therapy** is enabled, the landscape screen can show treatment markers and available IOB and COB data. These values can come from compatible Nightscout AID history or can be estimated locally from recorded treatments. Temporary basal data appears when it is available. A marker shows the current time when today is selected.

## iPad layout

On iPad, Home uses the additional screen space for a dashboard layout in both orientations. The current glucose and compact statistics can appear together above the main chart. Portrait also shows an Ambulatory Glucose Profile below the chart when enough history is available.

In landscape, select the expand button on the main chart to open a larger Ambulatory Glucose Profile view. It compares a selected day with recent history and shows Time in Range, average glucose, and coefficient of variation. Narrow app windows and larger accessibility text use a compact layout. See [iPad use](ipad.md).

## Sensor and data source information

The progress line near the bottom of the **Home** screen shows the estimated position in the active sensor lifetime when this information is available. Open **Settings > General > Home Screen > Sensor Lifetime** and select **Elapsed** or **Remaining**.

The section below the progress line shows the connected transmitter or follower source and indicates whether the connection has a problem. When sensor noise information is available, a coloured dot beside the data source shows its current status. Double-tap this section to open the related device or **Data Source** settings.

A warning can appear near the top of **Home** when xDrip4iOS detects prolonged sensor noise, an unchanged sensor signal, a temporary sensor issue, a sensor failure, or a transmitter failure. Select the warning to open the relevant Sensor or device screen. Select the close button after the warning has been reviewed.

Sensor noise describes how much readings vary. It does not measure glucose accuracy. Check a doubtful reading with an approved blood glucose meter and follow the instructions for the sensor.

## Home toolbar

The Home toolbar provides access to:

- [Snooze](snooze.md)
- [Glucose Readings](glucoseReadings.md)
- [Sensor Management](sensor.md)
- [Glucose Adjustments](glucoseAdjustments.md)
- [Quick Show/Hide](quickShowHide.md)
- [Screen Lock](screenLock.md).

Some controls appear only when the current source and settings support them.

When pump information is received from CareLink, select the pump section to open pump details. The CareLink screen can show delivery, active insulin, basal rate, sensor time remaining, pump status, battery, reservoir, communication, and reported pump limits when that information is available. The sensor and battery symbols change colour when attention may be needed.

When compatible AID information is received from Nightscout, the pump and Looping sections show the status for the time currently displayed on the chart. If the chart is moved into the past, these sections also change to historical information and use a faded appearance. Select the Looping section to open the full AID status screen.

The current Loop, CareLink pump, or CareLink SmartGuard state can also appear on supported widgets, Live Activities, and in the Apple Watch app. The symbol can show that the system is active, checking, suspended, disconnected, or has old data. xDrip4iOS displays the reported state. It does not control insulin delivery.

CareLink can provide IOB without reporting a pump. In that case, Home shows the IOB and its freshness without showing pump delivery information.

CareLink does not provide a changing COB value. xDrip4iOS can still estimate COB locally from recorded carbohydrate treatments when this is enabled by the selected treatment source. See [Treatment settings](treatmentSettings.md).

When Glucose Adjustments are active, press and hold the Glucose Adjustments button to show the original readings temporarily. Release the button to return to the adjusted readings.
