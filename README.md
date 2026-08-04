# 2 Ship 2 Harkinian – Android TV Port

An Android TV–focused fork of the Android port of **2 Ship 2 Harkinian**, optimized for use with a physical controller on devices such as Chromecast with Google TV.

## Credits

- Original project: [HarbourMasters/2ship2harkinian](https://github.com/HarbourMasters/2ship2harkinian)
- Original Android port: [Waterdish/2ship2harkinian-Android](https://github.com/Waterdish/2ship2harkinian-Android)
- Android TV fork and modifications: **Armster1991**

## Requirements

- Android 7 or newer
- OpenGL ES 3.0 or newer
- A legally obtained Majora's Mask ROM compatible with 2 Ship 2 Harkinian
- A physical controller is strongly recommended for Android TV devices

## Android TV Fork Features

- Appears directly in the Android TV / Google TV launcher.
- Includes an Android TV banner.
- Press **L1 + R1** to open or close the Enhancements menu.
- Press **L3 + R3** to close the application.
- Preserves the user's `mm.o2r` during application updates.
- Installs the included `2ship2harkinian.json` configuration only when no user configuration already exists.
- Never intentionally overwrites an existing user configuration during startup or update.
- Supports a preconfigured default setup, including 30 FPS when enabled in the included JSON configuration.

## Installation

1. Download the APK from this fork's Releases page:
   https://github.com/armster1991/2ship2harkinian-Android-TV/releases
2. Install the APK on the Android TV device.
3. Open the application once.
4. Grant the requested file permissions.
5. When prompted, choose to generate an O2R file.
6. Select the compatible Majora's Mask ROM from your device storage.
7. Wait for the extraction process to finish.
8. On subsequent launches, the application should start directly into the game.

The generated game files and configuration are stored in the `2S2H` folder at the root of the device's accessible storage.

## Controller Shortcuts

| Shortcut | Action |
|---|---|
| **L1 + R1** | Open or close the Enhancements menu |
| **L3 + R3** | Close the application |

The Android Back button may also open the Enhancements menu, depending on the device and controller.

## Default Configuration

This fork can include a default configuration file at:

```text
Android/app/src/main/assets/2ship2harkinian.json
```

On startup, the application copies it to:

```text
/2S2H/2ship2harkinian.json
```

The copy happens only when the destination file does not already exist. An existing configuration is preserved.

## Updating

The application refreshes its bundled program assets when its version changes, but the user's `mm.o2r` is preserved.

Even with this protection, keeping a backup of these files before installing a new build is recommended:

```text
/2S2H/mm.o2r
/2S2H/2ship2harkinian.json
```

## Mods

Place compatible mods inside the `2S2H` folder in the device's accessible storage. The exact subfolder structure may depend on the mod.

## Frequently Asked Questions

### The game crashes immediately. What should I check?

Confirm that `mm.o2r` was generated from a compatible ROM and was not corrupted during extraction. Keep a backup before deleting or regenerating it.

### The game opened once, but now only shows a black screen.

Avoid raising MSAA above `1` in **Settings → Graphics**. Revert the graphics configuration or restore a known working configuration if necessary.

### How do I open the Enhancements menu on Android TV?

Press **L1 + R1** on the controller.

### How do I close the application without returning through the menus?

Press **L3 + R3**.

### Where is the configuration file?

```text
/2S2H/2ship2harkinian.json
```

### Will an update erase my `mm.o2r`?

This fork removes the update routine that deleted `mm.o2r`. A backup is still recommended before testing a new build.

### My controller is not responding in the game.

Open the Enhancements menu and check **Settings → Controller → Controller Mapping**. Confirm that the controller is detected and use the refresh option when necessary.

### Does gyro aiming work?

Gyro support comes from the underlying Android port. When asked for an input device, press a controller button. If the controller has no compatible gyro, the application may use the Android device's sensors instead.

## Known Issues inherited from the Android port

- Orientation lock may not work correctly.
- Near-plane clipping can occur when the camera is close to walls.
- Pictograph Box images may render black on some devices or builds.
- Interface scaling options may be limited.

## Build Instructions

1. Install Android Studio and Android NDK 26 or newer.
2. Configure `Android/app/build.gradle` with the correct local NDK path when required by the project setup.
3. Ensure the default configuration file is present at:

```text
Android/app/src/main/assets/2ship2harkinian.json
```

4. Open the Android project in Android Studio.
5. Build the APK.

## Legal Notice

This repository does not provide copyrighted game ROMs. Users must supply their own legally obtained copy of The Legend of Zelda: Majora's Mask.
