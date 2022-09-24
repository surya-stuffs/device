# android_device_xiaomi_surya_twrp
For building TWRP for POCO X3 / X3 NFC (codenamed "karna / surya")

TWRP device tree for POCO X3 (karna/surya)

## Compile

First checkout minimal twrp with aosp tree:

```
repo init --depth=1 -u https://github.com/TheStrechh/platform_manifest_twrp_aosp.git -b twrp-12.1
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/surya" name="xiaomeme-surya/android_device_xiaomi_surya" remote="github" revision="twrp-12.1" />
```

Finally execute these:

```
. build/envsetup.sh
lunch twrp_surya-eng
make recoveryimage && ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/surya/recovery.img
```

## Other Sources

Using precompiled stock kernel.
