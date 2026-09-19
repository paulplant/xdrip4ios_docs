# Glucose Adjustments

Glucose Adjustments can change or smooth the values shown by xDrip4iOS. The original readings remain stored.

!!! warning "xDrip4iOS values will be different"
    If xDrip4iOS uses a Dexcom sensor in **Coexistence Mode** or receives readings in **Follower** mode, it receives glucose values from another app or service. Enabling **Adjustment** or **Smoothing** changes the values displayed by xDrip4iOS. The values in xDrip4iOS will then differ from the original data source. This is expected.

    Disable both **Adjustment** and **Smoothing** if xDrip4iOS should display the original values. You can also enable **Show Original Values** to compare the original and changed values.

    **OS-AID Share** sends unsmoothed data unless **Share Smoothed Data** is enabled. See [Glucose Adjustments and shared values](../services/osAidShare.md#glucose-adjustments-and-shared-values).

Select **Glucose Adjustments** in the toolbar at the top of **Home**. Choose the number of hours shown in the preview chart before changing the settings.

![The adjustment and smoothing options](../img/screenshots/source/glucoseAdjustmentsOptions.png)

## Adjustment

Glucose Adjustment is intended for sensors and follower sources that cannot be calibrated directly.

It is different from sensor calibration. Calibration changes how the sensor or xDrip algorithm calculates glucose. Adjustment changes the completed glucose value afterwards.

If the active sensor already has a suitable calibration process, xDrip4iOS disables Adjustment. This prevents two different correction systems from being applied to the same glucose values.

Adjustment is available for glucose sources where direct calibration is not available. This includes compatible factory-calibrated sensors and follower data sources.

### Add BG checks first

Before creating an adjustment, add recent BG checks to the chart. Ideally, use several checks from the previous 4 to 12 hours at different glucose levels:

- a lower glucose value
- a value within the normal range
- a higher glucose value

The BG checks appear as reference points in the live preview. Adjust the controls until the adjusted glucose curve follows these reference values as closely as possible.

The app does not calculate Scale or Emphasis automatically from the BG checks. The BG checks provide the real blood glucose values that you use to evaluate the live preview.

!!! warning
    Do not adjust the curve only because its shape looks better. The adjusted curve should be supported by reliable BG checks.

### Offset

Offset moves the complete glucose curve up or down by the same amount.

For example, an Offset of `+10 mg/dL` adds 10 mg/dL to every eligible reading. An Offset of `-10 mg/dL` subtracts 10 mg/dL.

You can set the Offset in two ways:

- Use the plus and minus buttons to move the value up or down.
- Select the glucose value shown beside Offset and enter a current BG value. xDrip4iOS calculates the required Offset automatically.

Offset is usually sufficient when the sensor curve has the correct overall shape but remains consistently above or below the BG checks.

### Scale

Some sensors produce a glucose curve that appears flatter or more exaggerated than the BG checks.

Scale changes the distance between lower and higher glucose values:

- `1.00` keeps the original range.
- A Scale below `1.00` pulls the curve inwards and reduces the difference between lower and higher values.
- A Scale above `1.00` stretches the curve outwards and increases the difference between lower and higher values.

For example, with Normal Emphasis and no Offset:

| Original | Scale 0.90 | Scale 1.10 |
| ---: | ---: | ---: |
| 70 mg/dL | 73 mg/dL | 67 mg/dL |
| 100 mg/dL | 100 mg/dL | 100 mg/dL |
| 200 mg/dL | 190 mg/dL | 210 mg/dL |

Use several BG checks at different glucose levels when changing Scale. The app warns when there are not enough BG checks visible in the preview.

Adjust Scale until the difference between the lower, in-range and higher parts of the curve matches the BG checks more closely.

### Emphasis

Emphasis changes which part of the glucose range is affected most by Scale.

- **Normal** applies Scale around the middle of the glucose range.
- **Highs** biases the Scale effect towards higher glucose values.
- **Lows** biases the Scale effect towards lower glucose values.

Emphasis does not make a separate adjustment. It changes the centre around which Scale stretches or compresses the curve.

Emphasis has no effect when Scale is `1.00`.

### Suggested workflow

1. Select a preview period containing several useful BG checks. Normally, use the previous 4 to 12 hours.
2. Enable **Adjustment**.
3. Set the Offset so the curve is generally aligned with the BG checks.
4. Compare the lower, in-range and higher parts of the curve.
5. If the curve is too flat or too exaggerated, adjust Scale.
6. If the Scale correction is needed mainly at higher or lower values, change Emphasis.
7. Continue adjusting Offset and Scale while watching the live preview.
8. Apply from **Now** first, or apply to the selected historical period when you are satisfied with the preview.

It can take some practice to balance Offset, Scale and Emphasis. The live preview allows you to see the combined result before applying it.

## Smoothing

Enable **Smoothing**, then select Light, Medium, or Strong. Select an **Algorithm**:

- **Savitzky-Golay** is the default. It smooths short sections while keeping the general shape of peaks and troughs.
- **Exponential** calms recent changes with less flattening.
- **Kalman** produces a steadier curve with more visible filtering.
- **LOESS** follows ramps and bends with a less rigid curve.
- **Hampel + Savitzky-Golay** first reduces isolated spikes, then smooths the wider curve.

Preview the result before applying it.

Smoothing can hide a real rapid change or make the chart appear delayed.

## Reading frequency

Some sources provide readings more often than every five minutes. When **Reading Frequency** is shown, enable **5-minute readings** to use one visible reading approximately every five minutes. Nightscout and Apple Health have separate options for storing the extra readings.

## Apply the changes

Under **Apply From**, select **Now** or an available period of recent history, then select **Apply**. Applying to a previous period replaces the displayed values for that period. Read any message below the selection because it states whether Nightscout or Dexcom Share data will also be updated.

## Original readings

Enable **Show Original Values** in **Quick Show/Hide** or under **Settings > General > Home Screen** to compare them with the adjusted readings. You can also compare both values in **Glucose Readings**.

When adjustments are active, press and hold the Glucose Adjustments button on **Home** to show the original readings temporarily.

!!! warning
    Glucose Adjustments change the values shown by xDrip4iOS. They cannot correct a faulty sensor. Keep original readings visible while testing a change and confirm doubtful values with an approved meter.
