# Widgets and Live Activities

xDrip4iOS can show glucose information in Home Screen widgets, Lock Screen widgets, StandBy, the Dynamic Island, and Live Activities where iOS supports them.

## Add a widget

1. Touch and hold an empty area of the iPhone Home Screen or Lock Screen.
2. Select the widget add control.
3. Search for xDrip4iOS.
4. Select an available size or accessory style.
5. Add the widget and place it where required.

The project provides small, medium, and large system widgets plus circular and rectangular accessory widgets.

## Live Activity

Open **Settings > Alerts and Notifications > Notifications** and enable **Live Activity**. Under **Style**, select Minimal, Normal, or Large. The presentation can include the Lock Screen, Dynamic Island, and StandBy layouts supported by the device.

Disabling the Live Activity keeps the selected style for the next time it is enabled. **Quick Show/Hide** on Home provides another Live Activity switch without changing the style.

When a Live Activity is enabled, the settings screen shows a preview of the selected layout. It uses the latest available information or example data when no current preview is available.

Live Activities are available in Master mode. In Follower mode, they require **Heartbeat** under **Settings > Data Source > Keep-alive** and a connected heartbeat device.

The preview shows how the selected layout is arranged. It does not start a Live Activity or confirm that iOS is currently updating one.

xDrip4iOS sends new readings to an active Live Activity when the app receives them, including during background updates. iOS controls when the update becomes visible and how long the Live Activity remains active. Reopen xDrip4iOS if iOS ends an activity or the displayed value becomes stale.

Supported detailed Live Activity layouts can show a coloured sensor noise indicator when this information is available.

Supported Live Activity layouts can also show the current Loop, CareLink pump, or CareLink SmartGuard state. The symbol and colour can indicate that the system is active, checking, suspended, disconnected, or has old data. xDrip4iOS only displays the state reported by the connected service.

When IOB or COB is available, the Live Activity settings show **Show IOB/COB**. This controls the values in the Large Lock Screen layout and the CarPlay or Smart Stack **Chart** layout. These values can come from an AID source or can be estimated from recorded treatments.

## Sensor warm-up

During sensor warm-up, supported Live Activity layouts show **Sensor warming up** and the expected completion time instead of a glucose value. This applies to the Lock Screen, Dynamic Island, CarPlay, and Apple Watch Smart Stack layouts.

After Dexcom warm-up finishes, the Live Activity can show **Warm-up complete** and **Waiting for first reading…** until the first glucose value arrives. This short waiting period does not mean that another warm-up has started.

The Shortcuts app also includes **Restart Live Activity**. You can use this action in a personal automation if you rarely open xDrip4iOS. The action requests a restart. It does not guarantee that iOS will keep the activity active.

## CarPlay style

On iOS 26 or later, a **CarPlay** section appears below the Live Activity settings when a Live Activity is enabled. Select **Style** and choose:

- **Chart** shows the current glucose, trend arrow, change, and recent glucose chart. It can also show current AID, IOB, and COB information when this is available. This is the default style.
- **Basic** uses the available space for a larger glucose value, trend arrow, and change. It does not show a chart.

The preview below the setting updates when the style is changed. It does not start a Live Activity or confirm that CarPlay is currently displaying one.

Apple uses this same compact Live Activity layout for CarPlay and the Apple Watch Smart Stack. Changing the CarPlay style can therefore change both displays.

CarPlay decides when and where a Live Activity is shown. The selected style changes its contents only.

## StandBy

StandBy uses the widget or Live Activity presentation selected by iOS. Advanced settings can allow high contrast or force large numbers. These options affect display only.

## Update timing

Widgets and Live Activities do not create glucose readings. They display data received by the main app. Their update can lag behind the Home tab because iOS limits extension refreshes.

In Follower mode, Home Screen widgets show **Keep-alive Disabled** when **Keep-alive** is **Disabled**. This warning replaces the glucose display so that an old value is not mistaken for a current reading. Open xDrip4iOS and select a background update method under **Settings > Data Source** to restore normal widget display.

!!! warning
    Check the timestamp. A widget can remain visible after the main app stops receiving data.
