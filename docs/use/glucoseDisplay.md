# Glucose Display

The **Glucose Display** section contains the glucose unit, Home Screen, Glucose Ranges, and Statistics settings.

## Blood Glucose Units

Select `mg/dL` or `mmol/L` before entering glucose ranges, alarm values, calibrations, or blood glucose treatments.

Changing the unit converts the way existing readings are displayed. It does not change the glucose value received from the sensor. Review all manually entered ranges and alarm values after changing it.

## Glucose ranges

Open **Settings > Glucose Display > Glucose Ranges**. Set the five marks in a logical order:

1. urgent high
2. high
3. target
4. low
5. urgent low.

Enter values in the currently selected glucose unit. The ranges determine colours, chart reference lines, and defaults used by related features. Alert thresholds are configured separately.

The detailed **Statistics** tab and PDF reports use standard clinical ranges. They can therefore show different percentages from Home when Home is configured to use personal glucose ranges.

## Home chart options

Use **Main Chart Hours** under **Settings > Glucose Display > Home Screen** to select a 3, 5, 8, 12, or 24-hour main range. The same control is available under **Quick Show/Hide > Glucose Chart**.

Spread two fingers on the main chart to zoom in to a shorter period. Pinch inward to zoom out to a longer period. One completed pinch changes one step. A short message shows the selected period. The setting and chart gestures all change the same saved range.

The mini chart can show 1, 2, 3, or 7 days. Treatments, original readings, and sensor noise appear when their related settings and data are available.

Enable **Show Sensor Noise** under **Settings > Glucose Display > Home Screen** or **Quick Show/Hide** to add shaded noise bands to the main chart. The bands help identify periods when the sensor signal was less stable. They do not show glucose accuracy.

Drag the main chart to inspect history. The large Home value becomes the latest value in the historical window and is visibly marked as historical. Double-tap to return to now.

The highlighted area in the mini chart represents the period shown in the main chart. Drag this area to move through history. Select the mini-chart period to choose its range. Double-tap the mini chart to move to the next period.

When screen rotation is enabled, landscape view compares the selected day with an Ambulatory Glucose Profile from recent history. Use the comparison menu to select the number of previous days. Swipe or use the side arrows to move between days. Double-tap the middle of the chart or the date to return to today. Double-tap the range summary to switch between Time in Range and Time in Tight Range.

When compatible Nightscout AID information is available, the right side can also show temporary basal changes, insulin on board, and carbohydrates on board for the selected day. Recorded insulin and carbohydrate treatments are marked on the related charts. This information is for review only. xDrip4iOS does not control insulin delivery.

When CareLink provides automatic basal information, open its settings from **Settings > Data Source > Status** to choose how it appears on the main chart. **Basal Pulses** shows each delivered amount as a short pulse. **Temp Basals** shows the equivalent U/hr rate between deliveries.

## Statistics

Enable statistics under **Settings > Glucose Display > Statistics**. Select the time-in-range calculation and whether estimated A1C is displayed in IFCC units where supported.

The Home period choices are today, 24 hours, 7 days, 30 days, and 90 days. A longer period can take more time to calculate and can include changes in sensor performance or therapy.

Statistics are only as complete as the stored readings. Connection gaps, deleted history, filtered invalid values, and a recent installation reduce coverage.

Open the **Statistics** tab for detailed CGM statistics, longer periods, trend charts, daily summaries, and PDF report generation. See [Statistics](statistics.md).
