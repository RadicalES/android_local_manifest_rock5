# Local manifest: AOSP 15 for Radxa ROCK 5

`repo` local manifest for the open, mainline-based AOSP port for the Radxa ROCK 5 family.
The device tree and its documentation are in
[android_device_radxa_rock5](https://github.com/RadicalES/android_device_radxa_rock5).

| Path | Repository | Branch |
|---|---|---|
| `device/radxa/rock5` | [RadicalES/android_device_radxa_rock5](https://github.com/RadicalES/android_device_radxa_rock5) | `main` |
| `vendor/google/graphics/desktop/mesa3d/panvk` | [RadicalES/mesa](https://github.com/RadicalES/mesa) (Mesa 26.0 + Soong build) | `android-15-rock5` |
| `external/minigbm` | [RadicalES/minigbm](https://github.com/RadicalES/minigbm) (replaces AOSP's) | `android-15-rock5` |

## Getting the source

```sh
mkdir aosp-15-rock5 && cd aosp-15-rock5
repo init -u https://android.googlesource.com/platform/manifest -b android-15.0.0_r32
git clone https://github.com/RadicalES/android_local_manifest_rock5 .repo/local_manifests -b android-15.0
repo sync -c -j8
```

The kernel is not part of the tree: build it with `device/radxa/rock5/kernel/build-kernel.sh` and copy
`Image` and the DTBs to `device/radxa/rock5-kernel/`. Building, the image script and flashing are
described in the device tree's README.

## Branches

One branch per Android version: `android-15.0`.

## License

Apache-2.0
