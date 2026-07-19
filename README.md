# One UI Home 36 Magisk Module

## DISCLAIMER
- One UI apps and blobs are owned by Samsung™.
- The MIT license specified here is for the Magisk Module only, not for One UI apps and blobs.

## Descriptions
Home launcher app by Samsung Electronics Co., Ltd. ported and integrated as a Magisk Module for all supported and rooted devices with Magisk

## Sources
- https://apkmirror.com com.sec.android.app.launcher (target SDK 36) & com.sec.android.provider.badge by Samsung Electronics Co., Ltd.
- BadgeSettings.apk by @KaldirimMuhendisi
- libmagiskpolicy.so: Magisk (stable) 30.7 (30700)

## Changelog

v1.8
- Fix a crash
- Fix NaN issue
- Prepare /storage/emulated/"$UID"/Android/data/com.sec.android.app.launcher/files directories

v1.7
- Fix recents provider doesn't launch sometimes with `su -c setprop persist.disable_recents_animation 1` (For more details, read Troubleshootings below)
- Revert unlinkToDeath in Y1.v.M
- Resets module folders/files permissions at post-fs-data
- Move _uninstall.log to /data/adb/logs/

v1.6
- Fix recents crash on newer SDK 36 version
- Fix wrong logic at isClassicDex & isNewDexMode methods
- Revert restart process on boot

v1.5
- Restarts process via service.sh to prevent unresponsiveness on boot if the recents provider is activated
- Resets module folders/files permissions at post-fs-data

v1.4
- Fix wrong logic in semDisplayDeviceType & getTopFocusedDisplayId method

v1.3
- Refix persistent bug crash/Application Not Responding at boot by removing unlinkToDeath in Y1.v.M method

v1.2
- Fix Application Not Responding at boot

v1.1
- Fix crash at boot in SDK 36 QPR2

v1.0
- Revert extending timeout (it was causing issue while launching apps)

v0.9
- Extend startRecentsTransition timeout & open timeout end
- Fix rootView isn't valid

## Screenshots
https://t.me/ryukimodsscreenshots/69

## Requirements
- NOT in One UI nor Touchwiz ROM
- Android 15 (SDK 35) and up
- Magisk or Kitsune Mask or KernelSU or Apatch installed
- One UI Core Magisk Module v2.1 or above installed https://github.com/reiryuki/One-UI-Core-Magisk-Module
- Add media page to Home screen option requires Google app installed https://play.google.com/store/apps/details?id=com.google.android.googlequicksearchbox or ported Samsung News/Free/Daily/Bixby Home app (com.samsung.android.app.spage) if it's exist.
- Recents provider requires Android 16 (SDK 36) and up
- Full gesture navigation and double tap to sleep requires root permission

## Installation Guide & Download Link
- Remove any other else One UI Home Magisk module with different name (no need to remove if it's the same name)
- Reboot
- If you are using KernelSU, you need to disable Unmount Modules by Default in KernelSU app settings and install https://github.com/KernelSU-Modules-Repo/meta-overlayfs or https://github.com/KernelSU-Modules-Repo/magic_mount_rs or https://github.com/KernelSU-Modules-Repo/hybrid_mount or https://github.com/maxsteeel/nomount first depending on ROM compatibility
- Install One UI Core Magisk Module first: https://github.com/reiryuki/One-UI-Core-Magisk-Module
- If you want to activate the recents provider, READ Optionals bellow!
- Install this module https://github.com/reiryuki/One-UI-Home-36-Magisk-Module via Magisk app or Kitsune Mask app or KernelSU app or Apatch app or Recovery if Magisk or Kitsune Mask installed
- Reboot
- If you are using KernelSU, you need to allow superuser list manually all package name listed in package.txt (enable show system apps) and reboot afterwards
- Change your default home to this launcher via Settings app (or you can copy the content of default.sh and paste it to Terminal/Termux app. Type su and grant root first!)
- If you want to use Add media page to Home screen option, you need to install Google app https://play.google.com/store/apps/details?id=com.google.android.googlequicksearchbox or ported Samsung News/Free/Daily/Bixby Home app (com.samsung.android.app.spage) if it's exist.
- If you want to change some configurations, read Troubleshootings bellow!
- If you are using multi user or Work Profile, don't forget to allow "Display over other apps" manually at the App Info or you can run this terminal command instead:

`su`

`appops set com.sec.android.app.launcher SYSTEM_ALERT_WINDOW allow`

## Optionals
- https://t.me/ryukinotes/33
- Global: https://t.me/ryukinotes/35

## Troubleshootings
- https://t.me/ryukinotes/33
- Global: https://t.me/ryukinotes/34

## Known Issues
- Open in pop up view doesn't work
- Hide apps on Home screen doesn't work
- Does not support navbar overlay if recents provider is activated
- Empty recents while pressing recents button directly from splitscreen. You have to relaunch one of the previously split apps to fix that.
- Recents tumbnails are blacked out in some ROMs. If your device supports vulkan, this module https://github.com/reiryuki/SKIA-UI-Renderer-Enabler-Magisk-Module may fix that.
- Edge panels doesn't work

## Support & Bug Report
- https://t.me/ryukinotes/54
- If you don't do above, issues will be closed immediately

## Credits and Contributors
- @KaldirimMuhendisi
- https://t.me/androidryukimodsdiscussions
- https://t.me/androidappsportdevelopment

## Sponsors
https://t.me/ryukinotes/25


