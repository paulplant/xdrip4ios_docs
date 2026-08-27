# Apple Watch

xDrip4iOS offers four ways to show glucose information on Apple Watch. They do not all update in the same way.

| Option | What it is | How it receives glucose |
| --- | --- | --- |
| xDrip4iOS Watch app | The xDrip4iOS app installed on Apple Watch | Requests current data from xDrip4iOS on the paired iPhone |
| xDrip4iOS complication | A complication supplied by xDrip4iOS | Receives background updates from the iPhone through the xDrip4iOS Watch app |
| Contact Image complication | Apple's Contacts complication showing an image created by xDrip4iOS | Uses the image of the xDrip4iOS contact stored on the iPhone |
| Calendar complication | Apple's Calendar complication showing an event created by xDrip4iOS | Uses the latest event in the calendar selected in xDrip4iOS |

The Watch app and xDrip4iOS complications require the xDrip4iOS Watch app to be installed. The Contact Image and Calendar options use standard Apple complications.

On supported systems, Apple Watch can also show the xDrip4iOS Live Activity in the Smart Stack. Apple uses the same compact layout for the Smart Stack and CarPlay. The **CarPlay > Style** choice under **Settings > Alerts and Notifications > Notifications** can therefore change both displays. See [CarPlay style](widgetsLiveActivities.md#carplay-style).

## xDrip4iOS Watch app

Install xDrip4iOS from the Watch app on the paired iPhone if automatic app installation is disabled.

The Watch app has three views:

- a chart with the current glucose, trend, reading age, data source, sensor information, sensor noise status, and pump or AID information when available
- the same chart with the recent Ambulatory Glucose Profile shown in the background
- a large glucose value with the change, trend, range indicator, and reading age.

Swipe between the views. The Ambulatory Glucose Profile view compares the current trace with the usual pattern calculated from recent iPhone history. It becomes available after the Watch receives enough history from the iPhone.

While the Watch app is open, it repeatedly asks the paired iPhone for current data. Double-tap the glucose information to request another update.

The Watch app does not connect directly to the CGM or an online Follower service. The iPhone must receive the reading first.

When sensor information is available, the Watch app uses the **Prefer Sensor Countdown** choice from **Settings > Glucose Display > Home Screen** on the iPhone. A coloured dot beside the data source can show the current sensor noise status.

When available, the AID row shows insulin on board, carbohydrates on board when the source provides it, the age of the latest activity, and the current Loop, CareLink pump, or CareLink SmartGuard state. The state can show that the system is active, checking, suspended, disconnected, or has old data. CareLink does not provide a changing carbohydrates on board value, so COB is not shown for a CareLink status. xDrip4iOS displays this information only.

## xDrip4iOS Watch complications

xDrip4iOS supplies inline, circular, rectangular, and corner complications. The available shapes depend on the selected watch face. Add an xDrip4iOS complication through the watch-face editor.

These complications can show:

- the current glucose and trend
- the change from the previous reading
- a glucose-range indicator
- the reading time
- a small chart on the rectangular complication.

Selecting an xDrip4iOS complication opens the xDrip4iOS Watch app.

In Follower mode, a complication shows a warning when **Keep-alive** is **Disabled**. The circular complication uses a warning triangle. Other supported layouts show a warning symbol or **Keep-alive disabled**. The old glucose value is hidden so that it is not mistaken for a current reading. Open the iPhone app and select a background update method to restore normal complication display.

### Why complication updates can be delayed

Apple does not allow a third-party complication to run continuously. [watchOS gives each active complication a limited update allowance](https://developer.apple.com/documentation/widgetkit/keeping-a-widget-up-to-date/). The allowance depends on whether the complication is visible and how the Watch is being used. Battery state and the connection between the iPhone and Watch can also affect delivery.

[Apple currently allows up to 50 priority complication updates from the iPhone each day](https://developer.apple.com/documentation/watchconnectivity/wcsession/remainingcomplicationuserinfotransfers) when the complication is on the active watch face. If it is not on the active face, this allowance is not available. When the allowance has been used, further information can still use normal background delivery, but it may arrive later.

xDrip4iOS uses the available update methods as follows:

- When the Watch app is open, it requests current data directly from the iPhone.
- When the Watch app is closed, the iPhone sends new data in the background.
- When an xDrip4iOS complication is active, the app requests a priority complication update about every 17 minutes when possible.
- Updates between those requests use normal background delivery.
- After new data reaches the Watch, xDrip4iOS asks watchOS to redraw the complication.

A request does not force an immediate update. Apple makes the final decision about when the information is transferred and when the complication is redrawn. This is why the Watch app can show a newer reading than the complication on the watch face.

## Contact Image complication

This option does not use an xDrip4iOS complication. It uses Apple's Contacts complication.

Enable **Settings > Sharing and Services > Contact Image** in xDrip4iOS. The app creates a contact named xDrip4iOS and updates its image with the latest glucose value. You can include the trend and use a high-contrast image. See [Contact Image](contactImage.md) for the full setup.

Add Apple's Contacts complication to the watch face and select the xDrip4iOS contact. Apple controls when the changed contact image is copied to the Watch, so the image can update later than the xDrip4iOS Watch app.

Full Contacts access is required. In Follower mode, **Keep-alive** cannot be Disabled because xDrip4iOS needs background updates to create a current image.

## Calendar complication

This option uses Apple's Calendar complication. It does not use an xDrip4iOS complication.

Enable **Settings > Sharing and Services > Calendar Share**. Select a dedicated calendar and choose whether the event includes the trend, change, unit, and glucose-range indicator. The Event Interval controls how often xDrip4iOS creates a new event when current readings are available. See [Calendar Share](../services/calendarShare.md) for the full setup.

Add Apple's Calendar complication to the watch face and make sure the selected calendar is visible on the Watch. Apple controls Calendar syncing and the complication display, so the event can update later than the reading on the iPhone.

Use a dedicated calendar for xDrip4iOS. This keeps glucose events separate from personal appointments and makes the correct calendar easier to select on the Watch.

## Which option should I use?

- Open the xDrip4iOS Watch app when you want the newest available reading and chart.
- Use an xDrip4iOS complication for the closest connection to the Watch app and a tap that opens xDrip4iOS.
- Use Contact Image when you prefer Apple's Contacts complication or a watch face that supports it.
- Use Calendar when you already use a calendar complication and want a configurable text display.

You can enable more than one option. Always compare the reading time because each option updates separately.

## If the Watch value is old

1. Confirm that **Home** on the iPhone shows a current reading.
2. Open xDrip4iOS on the Watch.
3. Double-tap the glucose information to request an update.
4. Confirm that the Watch is connected to its paired iPhone.
5. For an xDrip4iOS complication, confirm that it is on the active watch face.
6. For Contact Image or Calendar, confirm the related iPhone permission and Apple complication selection.

Remove and add a complication again only when it is missing or its layout is incorrect. Re-adding it does not remove Apple's update limits.

!!! warning
    A Watch value can be older than the iPhone value. Always check the reading time before using it.
