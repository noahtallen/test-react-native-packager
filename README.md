# Tests that the react-native packager launches for iOS

## The steps I followed to reproduce this:
1. `react-native init TestPackager` (and then verified that the packager launches)
2. Copied part of my Pod configuration for react-native from my other project, and ran `pod init` and `pod install`
3. I then removed all of the React libraries from my Xcode project, since they are now linked with Pods.
4. (In order to get this build working, I also removed all of the exteraneous test & tvOS targets)

## To test:
1. Verify that at the initial project creation (commit `752f72c`), running the project from Xcode _does_ launch the packager.
2. Verify that after installing React with Pods (commit `cdf0fd5`), running the project (via xcworkspace file) from Xcode does _not_ launch the packager.

_Addendum: for some reason, at step 1, `react-native run-ios` is successful. But at step 2, it was unable to complete the build. Perhaps something got cached that should not have. However, you can run both the working and non-working cases directly from Xcode. Don't forget to use the xcworkspace the second time, now that we're using pods!_