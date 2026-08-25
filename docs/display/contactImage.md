# Contact Image

Contact Image creates a contact whose image shows the latest glucose value.

## Configure the image

Open **Settings > Sharing and Services > Contact Image** and enable **Contact Image**. Allow Full Contacts access when iOS asks.

Choose:

- **Show Trend** to include the trend arrow
- **High Contrast** to use a simpler black and white image.

The preview on the settings screen updates as these options are changed. Use it to check the image before adding the contact to a Watch complication.

xDrip4iOS creates or updates a contact named xDrip4iOS. Full Contacts access is required. In Follower mode, **Keep-alive** cannot be Disabled.

Limited Contacts access is not enough because xDrip4iOS must be able to create and update the contact automatically.

## Apple Watch Contacts complication

Contact Image can supply glucose to Apple's Contacts complication. Add the Contacts complication to the watch face and select the xDrip4iOS contact.

This is an Apple complication, not an xDrip4iOS complication. xDrip4iOS updates the contact image when it receives a reading, but Apple controls when the changed image is copied to the Watch. The complication can therefore show an older value than **Home** or the xDrip4iOS Watch app.

Selecting this complication opens Apple's contact view. It does not open the xDrip4iOS Watch app.

## If the image does not update

1. Confirm that **Home** has a current reading.
2. Check that Contact Image is enabled and the preview is current.
3. Confirm Full Contacts access under the iPhone settings.
4. In Follower mode, confirm that **Keep-alive** is not Disabled.
5. Open the xDrip4iOS contact in Contacts and check its image.

If the contact is current but the Watch is not, the remaining delay is in Apple's contact and complication syncing.

## Privacy

The contact and its image can appear on shared devices, backups, and synced accounts. Use a suitable contact account and disable **Contact Image** if glucose information must not appear there.
