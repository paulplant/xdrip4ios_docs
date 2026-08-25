# Calendar Share

Calendar Share places glucose readings in a selected calendar. Another person can use the same shared calendar as a **Shared Calendar** follower in xDrip4iOS or Zukka.

It works with all releases of the app, including xDrip4iOS and Zukka. For example, one person can use xDrip4iOS and the other can use Zukka. They only need access to the same shared calendar.

Calendar Share can also provide glucose information for Apple's Calendar complication on Apple Watch.

## Prepare a shared calendar

Create a separate calendar in Apple's Calendar app and share it with each person who needs the readings. A shared iCloud calendar is recommended because it has been proven to be very reliable for this function. Each person must accept the calendar invitation before it can be selected in the app.

Do not use a calendar that contains personal appointments.

## Share readings from the source iPhone

1. Open **Settings > Sharing and Services > Calendar Share**.
2. Enable **Calendar Share** and allow Full Calendar access.
3. Select **Calendar To Use** and choose the shared calendar.
4. Enter an **Alias** to identify the person whose readings are being shared.
5. Check **Share Status**, **Last Value**, and the timestamp.

The source iPhone can receive its readings from a direct CGM or another follower service. Calendar Share is not available when the same iPhone is using **Shared Calendar** as its follower source.

## Include recent readings

**Include History** adds recent five-minute readings to each update. This helps follower phones fill missing readings after a short calendar sync or background update gap.

Use the shortest history period that works reliably. A longer period adds more information to every calendar update.

## Calendar event display

The preview shows how the event appears in Calendar. You can include the trend, change, unit, and glucose-range indicator in the visible event title.

**Event Interval** controls how often a new calendar event is created. Use a five-minute interval for normal follower updates. A longer interval also means that followers receive new values less often.

## Follow the shared readings

The receiving user selects `Shared Calendar` from **Data Source**, then selects **Status** to choose the shared calendar. See [Shared Calendar follower](../connect/sharedCalendar.md) for the complete setup.

## Apple Watch Calendar complication

Add Apple's Calendar complication to the watch face and make sure the selected calendar is visible on the Watch.

This is an Apple complication, not an xDrip4iOS complication. Apple controls Calendar syncing and when the complication redraws, so its reading can be older than **Home** or the xDrip4iOS Watch app.

## Calendar permission

Full Calendar access is required. In iOS, open **Settings > Apps > xDrip4iOS > Calendars** and select **Full Access** if Calendar Share cannot be enabled. When using Zukka, select Zukka instead.

## Privacy

Calendar events can appear on shared devices, notifications, backups, and synced accounts. Share the calendar only with people who should see the glucose information.
