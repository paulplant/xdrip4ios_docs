# Permissions and background operation

xDrip4iOS requests permissions only when a related feature needs them. iOS can change or revoke permissions later.

## Bluetooth

Bluetooth permission is required for direct CGM, heartbeat, and M5Stack devices. In iOS, open **Settings > Privacy & Security > Bluetooth** and confirm that xDrip4iOS is enabled.

When permission is denied or restricted, the affected device screen shows a Bluetooth permission warning instead of normal connection controls. Return to the screen after changing the iOS setting.

Keep Bluetooth enabled. A direct CGM connection can fail if the device is connected to the maximum number of phones or receivers that it supports.

## Notifications

Notification permission is required for reading notifications and xDrip4iOS alerts. Open **Settings > Notifications > xDrip4iOS** in iOS. Allow notifications and select the notification locations you need.

## Background App Refresh

Enable **Settings > General > Background App Refresh** for xDrip4iOS. iOS decides when normal background work can run, so follower downloads are not guaranteed to occur at an exact interval.

Under **Settings > Data Source**, **Keep-alive** offers Disabled, Normal, Aggressive, Continuous, and Heartbeat.

Start with Normal. If background readings are not reliable enough, try Aggressive. Continuous plays silent audio continuously while the app is in the background. It has the highest battery use and should only be used in extreme cases when Normal and Aggressive do not work well enough. Heartbeat requires a separately configured heartbeat device.

iOS makes the final decision about whether the app can remain active in the background. No Keep-alive option can guarantee that every update or alarm will arrive on time.

## NFC

Libre 2, Libre 2 Plus, Libre 3, and Libre 3 Plus direct connection requires an NFC scan during setup. Hold the top of the iPhone close to the sensor and keep it still until the scan finishes.

## Apple Health, Calendar, and Contacts

These permissions are requested only when the related feature is enabled. Denying one does not stop the main glucose display. It only stops that feature.

Calendar Share and Shared Calendar follower mode require Full Calendar access. Both features also need internet access so the shared calendar can sync between users. A shared iCloud calendar is recommended because it has been proven to be very reliable for this function.

## Battery and app termination

Do not routinely force-quit xDrip4iOS. A force-quit app cannot perform normal background work. Low Power Mode and Focus settings can also affect background updates and notifications.
