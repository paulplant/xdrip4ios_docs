# Medtrum EasyView follower

Medtrum EasyView follower mode downloads glucose information from a Medtrum EasyView account.

The Medtrum system must upload a current reading to EasyView before xDrip4iOS can receive it.

## Before you configure it

- Confirm that the account can see a current glucose reading in EasyView.
- Know whether it is a patient account or a caregiver account.
- For a caregiver account, confirm that the person you want to follow appears in its patient connections.

## Configure

Under **Settings > Data Source**, select **Follower**, then select `Medtrum EasyView` from **Data Source**. Select **Status** to open the Medtrum EasyView settings.

Enter the account email address and password in **Account**, then select **Log In**. The **Connection** section shows the login state. The optional alias, account type, and patient selection appear in **Profile**. Select the correct patient if the caregiver account has more than one connection. Confirm that **Home** shows a current reading.

If the account contains only one patient connection, xDrip4iOS can select it automatically. A personal account does not require a caregiver selection.

The **Activity** section shows the last connection and reports when the patient list could not be obtained. Use **Log Out** at the top of the screen when the account must be disconnected.

## Login errors

xDrip4iOS stops repeated attempts after the service reports invalid credentials. Correct the credentials before trying again. If a previously selected patient no longer exists, the app resets the patient selection.

If the service cannot refresh the patient list, the **Activity** section can show that the saved list is being used. Review the patient selection again after the service becomes available.

## Background updates

Medtrum EasyView follower needs internet access and background opportunities from iOS. Start with **Normal** under **Settings > Data Source > Keep-alive**. Try **Aggressive** only if needed. Use **Continuous** only in extreme cases because it has the highest battery use.

Do not force-close xDrip4iOS. If the connection is active but the reading is old, check the latest value in EasyView. xDrip4iOS cannot download a reading that has not reached the service.

## OS-AID sharing

Medtrum EasyView readings are not shared with OS-AID apps by default. **Share Medtrum Nano Pump CGM** is available with a warning under **Settings > Sharing and Services > OS-AID Share**. Leave it disabled unless you understand the warning and specifically need this connection.

For data relayed directly by the Medtrum Nano Pump instead, use [Medtrum Nano Pump](medtrum.md).
