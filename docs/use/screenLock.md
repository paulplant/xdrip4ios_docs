# Screen Lock

Screen Lock keeps xDrip4iOS awake when the glucose screen needs to remain visible.

## Clock Mode

Quickly tap the lock button in the toolbar at the top of **Home** to enable Clock Mode. The lock symbol becomes filled but keeps its normal toolbar colour.

Clock Mode changes **Home** into a simple current-status display:

- The glucose value and clock use large, bold text.
- The reading age and glucose change use larger text and scale down when more space is needed.
- The current Loop, open-source AID, or CareLink status symbol appears beside the glucose change when it is available.
- Other Home panels are hidden.
- The main chart returns to the current time and hides treatment markers.
- It temporarily uses a three-hour period, or five hours on iPad in landscape.
- Drag, pinch, and double-tap chart gestures are disabled.

The temporary period does not replace the chart period saved in Settings. The saved period, treatment markers, and normal chart gestures return when Clock Mode ends.

In iPhone portrait and on iPad, touch anywhere on the locked display to leave Clock Mode. On iPhone in landscape, rotate back to portrait and then touch the display. This prevents an accidental touch from closing the landscape display.

The touch-to-unlock area remains active when **Lock Screen Dimming** is Disabled, although it is transparent. Screen Lock also ends when a Home toolbar screen opens, another tab is selected, **Home** is left, or xDrip4iOS moves to the background.

On iPhone in landscape, Clock Mode places the glucose reading and optional clock beside the chart. On iPad, portrait places the glucose reading, chart, and optional clock vertically. iPad landscape places the glucose reading and optional clock beside each other above the chart.

## Keep the normal Home screen awake

Press and hold the toolbar lock button to keep the screen awake without enabling Clock Mode. The normal Home layout remains visible and interactive. The lock symbol becomes filled and red to distinguish this mode from Clock Mode.

Quickly tap the red lock button to return to normal screen behaviour. This mode also ends when a Home toolbar screen opens, another tab is selected, **Home** is left, or xDrip4iOS moves to the background.

## Configure the display

Open **Settings > General > Home Screen**:

- **Chart Rotation** allows the iPhone Home screen to use its landscape chart.
- **Lock Screen Clock** adds the clock to Clock Mode.
- **Lock Screen Dimming** selects Disabled, Dimmed, Dark, or Very Dark.

Screen Lock prevents the normal automatic display sleep while it is active. Keep the device connected to power during long use to avoid excessive battery drain.

StandBy is a separate iOS display function. Its high-contrast and large-number choices are available in **Advanced Settings**.

!!! warning
    Clock Mode intercepts touches until it is cancelled. The normal-layout keep-awake mode remains interactive. Neither mode is an iPhone or iPad security lock, and neither mode protects access to other apps.
