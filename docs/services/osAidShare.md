# OS-AID Share

xDrip4iOS can share glucose with a compatible open-source automated insulin delivery app and display selected AID information from Nightscout.

## Share with an AID app

A custom build can share readings with a compatible AID app when both apps were built for the same App Group. This cannot be changed after the apps are installed.

Open **Settings > Sharing and Services > OS-AID Share** and select the supported share type. The same screen contains **OS-AID Share Delays** when sharing is enabled.

If **OS-AID Share** is not shown, the installed build was created without this sharing feature.

When **Trio** is selected, xDrip4iOS also shares available information about the data source, sensor session, latest communication, transmitter battery, calibration state, and current sensor condition. A compatible Trio version can use this to show the sensor type, warmup or expiry state, expected sensor end, battery information, and warnings such as sensor noise or a temporary sensor issue.

This extra information is added without changing the established glucose-reading format. Older Trio versions continue to receive glucose readings and ignore information they do not support.

## Glucose Adjustments and shared values

OS-AID apps normally expect unsmoothed glucose values because they apply their own calculations. xDrip4iOS therefore shares unsmoothed values by default, even when smoothing is enabled in **Glucose Adjustments**. The value shown in xDrip4iOS can then differ from the value received by the AID app.

**Share Smoothed Data** is available only as a warned option. Leave it disabled unless the instructions for the AID app specifically require smoothed data. xDrip4iOS can turn this option off when the sharing or smoothing settings change, so review any warning shown on the **OS-AID Share** screen.

## Medtrum sources

Glucose received directly through the Medtrum Nano Pump cannot be shared with an OS-AID app. **OS-AID Share** is shown as Disabled while this is the direct CGM source.

Medtrum EasyView follower readings are not shared with OS-AID apps by default. **Share Medtrum Nano Pump CGM** is available with a warning for this follower source. Leave it disabled unless you understand the warning and specifically need this connection. An OS-AID app can use the shared readings for insulin dosing.

## Nightscout AID status

When Nightscout provides compatible AID and profile information, **Home** can show pump and AID status. Select the AID status section on **Home** to see available details such as:

- system and app version
- uploader battery
- pump reservoir, battery, and status
- the current recommendation and action reported by the AID system
- profile basal rates, insulin sensitivity, and carbohydrate ratios.

xDrip4iOS only displays this information. It does not calculate or control insulin delivery.

When enough history is stored, the **Trends** screen in **Statistics** can show average insulin and carbohydrate trends. The landscape Home screen can show temporary basal changes, insulin on board, and carbohydrates on board for the selected day. PDF reports can include Looping Success and recent AID information. See [Statistics](../use/statistics.md).

If older AID history is needed, use **Settings > Data Management > Import Data > Nightscout** and include **Device Status**.

## Safety boundaries

!!! warning
    Follow the build instructions for the selected AID app. An incorrect App Group stops data sharing. Confirm the glucose value and reading time inside the AID app before relying on the connection.

Do not add a delay or adjust readings unless the AID instructions require it. Keep original readings visible while testing a change. Review every warning shown beside **OS-AID Share** before using the connection.
