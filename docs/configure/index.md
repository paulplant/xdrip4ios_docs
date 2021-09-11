# General Settings

<img src="../img/Settings.png" style="zoom:75%;" />

In a [previous section](../connect/index.md), you should have initially configured xDrip4iOS to use **mg/dl** or **mmol/l** and to act as a **Master** or **Follower** device.

Now we can start to configure the app to work as we want. When you first install xDrip4iOS, we will put some default values that should work fine for most users to start using the app with.
___
## Show Notifications

You can enable xDrip4iOS to show a notification on your phone every 5 minutes. This will appear as per the Notification settings for xDrip4iOS in your iPhone settings. You can enable banner notifications and chose if it will show on the lock-screen or not.

<img src="img/SettingsNotification.png" style="zoom:50%;" />

<img src="img/Notification.png" style="zoom:50%;" />

You can also enable the App Badge which will should your current BG value on the app icon.

<img src="img/SettingsNotifBadge.png" style="zoom:50%;" />

<img src="img/Badge.png" style="zoom:54%;" />

!!!info "Decimals"
    When using mmol/l the App Badge will display decimals only if Show BG in Notifications is enabled.

<img src="img/SettingsBadge.png" style="zoom:50%;" />

If you disable Notifications you can use multiply by 10 to show the full value (you'll need to mentally add the decimal point. 94 means 9.4 mmol/l).

<img src="img/SettingsBadge10.png" style="zoom:50%;" />

___
## Objective Values

We think of objective values as our working limits. We define theses limits as being:

- <span style="color:green">**in range**</span>
- <span style="color:orange">**out of range**</span>
- <span style="color:red">**out of range (urgent)**</span>.

### ![](./../img/circle_green.png) In Range

Firstly we need to set a range where we want our glucose to be most of the time. This is set using ``Low Value`` and ``High Value``. Whilst our blood glucose value is between these limits, we will see the glucose points and values in <span style="color:green">**green**</span>.

### ![](./../img/circle_yellow.png) Out of Range

When our glucose values are below our Low value or above our High value, but still not anything to be worried about, then we will see them in <span style="color:orange">**yellow**</span>. We might use this as a sign that we should think about taking some kind of action (eat something or take insulin) before the values become "urgent".

### ![](./../img/circle_red.png) Out of Range (Urgent)

When our glucose values are above or below our "Urgent" values, then we consider them to need urgent attention and we will see them in <span style="color:red">**red**</span>. We set these limits using the ``Urgent Low Value`` and ``Urgent High Value`` We should take evaluate the situation and decide if we must take action (eat glucose or take insulin).

<img src="img/Values.png" style="zoom:50%;" />


___
## Graph Options

xDrip4iOS allows us to show the main graph in two ways:

### Dynamic y axis

This option (used by default) will use our **objective values** (see above) to define the values shown on the vertical axis. It will also show guidelines across the graph so that we can easily see how close we are to each limit.

<img src="img/yDynamic.png" style="zoom:50%;" />

The graph will automatically scale if our blood glucose value is above our Urgent High value.

### Standard Grid

By deselecting the dynamic graph option, xDrip4iOS will just show a default grid system.

<img src="img/yStatic.png" style="zoom:50%;" />

Again, the graph will scale as needed.