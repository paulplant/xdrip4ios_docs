# Build from source

Build xDrip4iOS from the current xdripswift repository when you need a personally signed installation.

## Requirements

- a Mac that can run a compatible Xcode release
- Git
- an Apple ID added to Xcode
- an iPhone running iOS 16.2 or later, or an iPad running iPadOS 16.2 or later
- unique bundle and App Group identifiers.

The Xcode workspace contains the main iPhone and iPad app, widgets and Live Activity extension, Apple Watch app, Watch complications, and a notification extension. All enabled targets must use compatible signing.

## Get the source

Clone the official repository and open `xdrip.xcworkspace` in Xcode. Pull updates only after preserving your local configuration and reviewing source changes.

## Create the override configuration

Use `xDripConfigOverride.xcconfig` for personal identifiers and build-specific options. Do not publish personal team identifiers, App Groups, service credentials, or signing values.

At minimum, configure a unique main bundle identifier and an App Group that your signing account can use. Extension bundle identifiers are derived from or must remain compatible with the main identifier according to the project configuration.

If integrating with an open-source AID app, use the exact shared App Group expected by that app. Confirm that both signing profiles contain it.

If the build must not share readings through an OS-AID App Group, add this line to `xDripConfigOverride.xcconfig`:

```text
DISABLE_LOOP_SHARE = YES
```

This hides **OS-AID Share** and disables its outgoing data. It does not change an OS-AID Follower data source.

## Select signing

1. Open the workspace in Xcode.
2. Select the xDrip project and each enabled target.
3. Select your development team.
4. Resolve all signing and capability errors.
5. Connect and trust the iPhone or iPad.
6. Select that device as the run destination.
7. Build and run.

With a free account, iOS can require frequent re-signing. A paid account has different certificate and provisioning periods.

## Update a source build

Commit or back up your override file and any intentional source changes. Pull the new source, resolve conflicts without replacing the project defaults blindly, reopen the workspace, and build over the installed app with the same bundle identifier. Changing the bundle identifier creates a separate app and does not update the existing installation.

## Build problems

- Open the workspace so package dependencies resolve correctly. Do not open the project file by itself.
- Confirm the selected Xcode version supports the project's iOS SDK.
- Resolve Swift package dependencies from Xcode.
- Check that every extension uses the same signing team and compatible App Group.
- Check that the bundle identifiers are unique to your account.
- Record the error before cleaning the build folder. Cleaning does not fix signing configuration.
