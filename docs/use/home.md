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

The main chart shows recent readings and can also show treatments, calibrations, original readings, glucose-range lines, sensor noise, and AID information when enabled.

- Drag horizontally to view earlier data.
- Double-tap the chart to return to the current time.
- Spread two fingers on the chart to zoom in to a shorter period.
- Pinch the chart inward to zoom out to a longer period.
- Select **Main Chart Hours** under **Quick Show/Hide > Glucose Chart** to choose the range directly.
- When the chart is moved into the past, the large value changes to the latest reading visible at the chart's end time. The value is shown as historical, not current.

The main chart periods are 3, 5, 8, 12, and 24 hours. A short message shows the selected period after a successful pinch.

[Clock Mode](screenLock.md) returns the chart to the current time and temporarily selects a range for its layout. It does not replace the saved chart period.

The mini chart provides a 1, 2, 3, or 7-day overview. Drag the highlighted time window to move the main chart through the stored history. Select the mini-chart period to choose a range, or double-tap the mini chart to move to the next period.

## Statistics

When enabled, the statistics area shows low, in-range, and high percentages, average glucose, estimated A1C or GMI information, coefficient of variation, and a time-in-range chart. Use the period menu below the chart to view today, 1 day, 7 days, 30 days, or 90 days.

Statistics require enough valid readings. They are informational and depend on the glucose ranges configured in **Settings**.

Open **Statistics** for more detailed statistics, longer periods, trend charts, daily summaries, and PDF report generation.

## Landscape chart

Rotate the iPhone to landscape when rotation is enabled to compare one day of glucose readings with an Ambulatory Glucose Profile from recent history. Use the comparison menu to select the number of previous days. This makes it easier to see where the selected day followed or differed from the recent pattern.

Swipe left or right, or select the arrows at the sides, to change the day. Double-tap the middle of the chart or the date to return to today. Double-tap the range summary to switch between Time in Range and Time in Tight Range.

When compatible Nightscout AID information is available, the landscape screen also shows temporary basal changes, insulin on board, and carbohydrates on board for the selected day.

## iPad layout

On iPad, Home uses the additional screen space for a dashboard layout in both orientations. The current glucose and compact statistics can appear together above the main chart. Portrait also shows an Ambulatory Glucose Profile below the chart when enough history is available.

In landscape, select the expand button on the main chart to open a larger Ambulatory Glucose Profile view. It compares a selected day with recent history and shows Time in Range, average glucose, and coefficient of variation. Narrow app windows and larger accessibility text use a compact layout. See [iPad use](ipad.md).

## Sensor and data source information

The progress line near the bottom of the **Home** screen shows the estimated position in the active sensor lifetime when this information is available. It normally shows elapsed time. Open **Settings > Glucose Display > Home Screen** and enable **Prefer Sensor Countdown** to show the estimated time remaining instead.

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

CareLink can provide entered meal amounts but does not provide a changing carbohydrates on board value. The Home and Apple Watch status areas therefore do not show COB when CareLink supplies the status.

When Glucose Adjustments are active, press and hold the Glucose Adjustments button to show the original readings temporarily. Release the button to return to the adjusted readings.
