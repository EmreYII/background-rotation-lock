# Background Rotation Lock

An experimental Windows plugin for ZBrush that helps prevent accidental left-drag view rotation on a calibrated, flat-color background.

[**Download the plugin ZIP**](Background_Rotation_Lock.zip?raw=true)

## Install and use

1. Close ZBrush and extract the ZIP.
2. Copy `Background_Rotation_Lock.zsc` and the complete `BackgroundRotationLockData` folder into `ZStartup\ZPlugs64` in your ZBrush 2022 installation.
3. Restart ZBrush and open **ZPlugin > Background Rotation Lock**.
4. In **3D Edit mode**, click **Enable / Disable**, then click and release once on empty, evenly colored background to calibrate.

The two controls are **Enable / Disable** and **Info**. The plugin starts **OFF** each time ZBrush launches.

## Compatibility and limits

**Version 0.2 experimental. Tested with ZBrush 2022.0.8 on Windows x64.** Newer ZBrush versions have not been verified. A macOS version is not available yet, but it may be released in the future.

Detection uses visible pixel colors. A model surface matching the background can also be blocked; gradients and overlays may affect detection. Middle/right mouse buttons and Ctrl/Alt gestures are excluded from filtering. The plugin does not create navigation mappings; middle-button orbit has not been verified.

See [INSTALLATION.md](INSTALLATION.md) for full setup and removal instructions. Source code and test details are included in the ZIP.
