# Personal TestFlight

A paid Apple Developer Program member can distribute a personally configured xDrip4iOS build to selected App Store Connect users through internal TestFlight testing.

## Responsibilities

The publisher controls signing, tester access, updates, and build availability. TestFlight builds remain available for 90 days. Do not invite a person unless you can maintain replacement builds and communicate when access will end.

xDrip4iOS is free and open source. Do not charge for access to a community build.

## Before uploading

1. Build and test xDrip4iOS on a physical iPhone or iPad.
2. Use a unique bundle identifier and correct App Group.
3. Confirm signing for the main app and every enabled extension.
4. Increment the build number for every upload.
5. Remove personal service credentials from the build configuration.

## Archive and upload

1. In Xcode, select a generic iOS device destination suitable for archiving.
2. Select **Product > Archive**.
3. In the Organizer, validate the archive.
4. Distribute it to App Store Connect.
5. Wait for Apple to process the build.

Apple associates an upload with its App Store Connect app by bundle ID and version information. Follow Apple's current [Upload builds](https://developer.apple.com/help/app-store-connect/manage-builds/upload-builds/) instructions when the Xcode interface differs from these steps.

## Add internal testers

1. Add each tester as an App Store Connect user with appropriate access to the app.
2. In the app's **TestFlight** tab, create or select an internal testing group.
3. Add the processed build to the group.
4. Invite the eligible App Store Connect users.
5. Ask each person to accept and install through Apple's TestFlight app.

Apple currently permits up to 100 internal testers, who must be App Store Connect users with access to the content. Follow Apple's current [Add internal testers](https://developer.apple.com/help/app-store-connect/test-a-beta-version/add-internal-testers/) instructions for roles and portal steps.

## Internal and external testing

External testing is a separate TestFlight process and requires Apple's beta review. Do not create a public external test as a shortcut for a private personal group. The publisher is responsible for complying with Apple's current programme rules.

## Publish an update

Pull and review the new xdripswift source, preserve the same identifiers, increment the build number, test, archive, and upload. Add the processed build to the existing internal group. Notify testers before the previous build expires.
