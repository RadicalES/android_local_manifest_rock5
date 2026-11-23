# Local manifest: AOSP 15 for Radxa ROCK 5

`repo` local manifest for the open, mainline-based AOSP port for the Radxa ROCK 5 family.
The device tree and its documentation are in
[android_device_radxa_rock5](https://github.com/RadicalES/android_device_radxa_rock5).

| Path | Repository | Branch |
|---|---|---|
| `device/radxa/rock5` | [RadicalES/android_device_radxa_rock5](https://github.com/RadicalES/android_device_radxa_rock5) | `main` |
| `device/radxa/rock5-kernel` | [RadicalES/android_device_radxa_rock5-kernel](https://github.com/RadicalES/android_device_radxa_rock5-kernel) (prebuilt kernel + U-Boot) | `android-15-rock5` |
| `vendor/google/graphics/desktop/mesa3d/panvk` | [RadicalES/android_external_mesa](https://github.com/RadicalES/android_external_mesa) (Mesa 26.3.1 + Rocket/Teflon NPU, Soong build) | `android-15-rock5` |
| `external/minigbm` | [RadicalES/android_external_minigbm](https://github.com/RadicalES/android_external_minigbm) (replaces AOSP's) | `android-15-rock5` |
| `hardware/interfaces` | [RadicalES/android_hardware_interfaces](https://github.com/RadicalES/android_hardware_interfaces) (replaces AOSP's; Bluetooth HAL rfkill fix) | `android-15.0` |
| `packages/apps/Settings` | [RadicalES/android_packages_apps_Settings](https://github.com/RadicalES/android_packages_apps_Settings) (replaces AOSP's; Ethernet IP + NTP, network adb, orientation, keep screen on, no-Wi-Fi fixes) | `android-15.0` |

## Getting the source

```sh
mkdir aosp-15-rock5 && cd aosp-15-rock5
repo init -u https://android.googlesource.com/platform/manifest -b android-15.0.0_r32
git clone https://github.com/RadicalES/android_local_manifest_rock5 .repo/local_manifests -b android-15.0
repo sync -c -j8
```

Building, the SD image script and flashing are described in the device tree's README:

```sh
. build/envsetup.sh && lunch aosp_rock5b-bp1a-userdebug && m
device/radxa/rock5/tools/mkimg.sh
```

## Branches

One branch per Android version: `android-15.0`.

## License

Apache-2.0
