# Background Rotation Lock installation

Background Rotation Lock helps prevent accidental left-drag view rotation on a calibrated, flat-color ZBrush background. This experimental release uses visible color, so a model surface matching the background color can also be affected.

Version: **0.2 experimental**. Tested with **ZBrush 2022.0.8 on Windows x64**. Use in **3D Edit mode**. Other ZBrush versions are unverified; no macOS build is included.

## Install

1. Close ZBrush.
2. Extract the plugin ZIP, `Background_Rotation_Lock.zip`. Open the extracted `Background_Rotation_Lock` folder.
3. Copy these two items directly into your ZBrush installation's `ZStartup\ZPlugs64` folder:
   - `Background_Rotation_Lock.zsc`
   - The complete `BackgroundRotationLockData` folder, including `BackgroundRotationLock.dll`.
4. Start ZBrush.
5. Open **ZPlugin > Background Rotation Lock**. You should see **Enable / Disable** and **Info**.

For the tested installation, the final structure is:

```text
C:\Program Files\Pixologic\ZBrush 2022\ZStartup\ZPlugs64\
    Background_Rotation_Lock.zsc
    BackgroundRotationLockData\
        BackgroundRotationLock.dll
```

If ZBrush is installed elsewhere, use that installation's `ZStartup\ZPlugs64` folder. Copy the ZSC file and data folder into it directly, rather than nesting the outer download folder inside it. The TXT and C source files are not required to run the plugin.

## Enable the lock

1. Open a 3D model and enter **Edit mode**. Display the normal canvas and close LightBox or other overlays.
2. Click **ZPlugin > Background Rotation Lock > Enable / Disable**.
3. Without holding Shift, Ctrl, Alt or another mouse button, click and release once on an **empty, evenly colored background area**. Do not click the model.
4. Left-drag on that background to check the lock. Use **Info** to view its state and instructions.

**Blue means enabled.** Immediately after enabling, calibration is still pending until you make the background click. Info shows `WAITING` while a background click is needed and `ENABLED` after calibration succeeds.

Click **Enable / Disable** again to switch the lock off and restore normal left-button navigation. Release all mouse buttons before switching it off.

## Recalibrate

Each activation requests a fresh background sample. After changing the layout, window size, display setup or background, disable and enable the lock again, then click the empty background once.

The plugin loads into the menu after each ZBrush launch but starts **OFF**. Activate and calibrate it for the new session. Disable it before leaving 3D Edit mode or working in 2.5D.

## Navigation and detection limits

The filter excludes middle/right mouse buttons and Ctrl/Alt gestures. It does not assign new mouse navigation mappings. Rotation through a separate MiddleButton plugin has not yet been verified in a drag test.

Detection matches the exact visible background color rather than testing mesh geometry. A matching model surface can be blocked. Gradients, reference images, overlays and the narrow canvas border may leave background areas unrecognized.

## Troubleshooting

- **The menu is missing:** close ZBrush, check the file structure above and restart. Confirm that you copied the compiled `.zsc` file and the complete data folder into the installation you actually launched.
- **The switch is blue but the view still rotates:** finish the empty-background click. If Info still says `WAITING`, choose another uniform, empty area. For a changed layout or background, disable and enable again before sampling.
- **A brush stroke on the model is blocked:** disable the lock. The model may match the calibrated background color; use a visually distinct, uniform background and recalibrate before trying again.
- **Disabling reports an unfinished gesture:** release all mouse buttons, click an unused interface area once, then try disabling again.

## Update or remove

To update, close ZBrush, back up the existing plugin file and data folder, then replace them with the new package. Keep the relative file structure intact.

If updating from **noviewerotate**, move its old `noviewerotate.zsc` startup file out of `ZStartup\ZPlugs64` and keep it as a backup before installing this version. Load one version at a time.

To uninstall, close ZBrush and remove only `Background_Rotation_Lock.zsc` and its `BackgroundRotationLockData` folder from `ZStartup\ZPlugs64`. Restart ZBrush.
