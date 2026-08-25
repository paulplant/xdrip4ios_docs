# Apple Health

xDrip4iOS can store glucose readings in Apple Health when Health access is enabled.

Apple Health is available on iPhone. The setting is unavailable when Health data cannot be used on the device.

## Enable Apple Health

1. Open **Settings > Sharing and Services > Apple Health**.
2. Enable **Write to Apple Health**.
3. Approve glucose write permission when iOS asks.
4. Open the Health app after new readings arrive and confirm the source and timestamps.

By default, xDrip4iOS limits Apple Health writes to the normal five-minute glucose interval. If the source supplies more frequent readings, **Frequent HealthKit Writes** under **Advanced Settings** can store those additional values. Most users should leave it disabled.

Enabling Apple Health does not import glucose readings from Health into xDrip4iOS. It only writes readings received by the app.

## Duplicate data

Apple Health can contain data from several sources. Health applies its own source-priority rules for display and analysis. Disable one uploader if identical readings are stored twice.

In the Health app, review **Blood Glucose > Data Sources & Access** to see which apps are writing values and to adjust their display priority.

## Privacy

Health data is managed by iOS and the user's Health permissions. Disabling the xDrip4iOS setting stops future writes. It does not delete entries already stored in Apple Health.

If permission was denied, change it in the Health app before enabling the xDrip4iOS setting again.
