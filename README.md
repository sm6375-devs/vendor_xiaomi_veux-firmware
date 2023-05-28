# Firmware tree for `Veux`

## What is this?

A firmware tree to ship firmware with builds for the POCO X4 Pro 5G / Redmi Note 11 Pro+ 5G.

# Getting started

First of all, ensure you have cloned this into
`vendor/xiaomi/veux-firmware`.

Manifest:

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest>
    <remote name="yourremote" revision="main" clone-depth="1" />
    <project name="vendor_xiaomi_veux-firmware" path="vendor/xiaomi/veux-firmware" remote="yourremote" />
</manifest>
```

Device tree dependencies file:

```
[
  {
    "remote": "yourremote",
    "repository": "vendor_xiaomi_veux-firmware",
    "target_path": "vendor/xiaomi/veux-firmware",
    "branch": "main",
    "clone_depth": "1"
  }
]
```

Manual cloning:

```bash
git clone <url of this repo> -b main vendor/xiaomi/veux-firmware --depth=1 --no-tags --single-branch
```

> These are example entries, you need to replace the relevant stuff
> with your own case.

After that, ensure your tree's BoardConfig inherits this tree's BoardConfigVendor:

```makefile
include vendor/xiaomi/veux-firmware/BoardConfigVendor.mk
```

> These kinds of includes are typically placed along with other
> inherits at the beginning of BoardConfig or at the end of
> BoardConfig, along with other includes if any.

# Additional information for geeks

## Firmware

**ROM**: MIUI

**Version**: 13.0.7.0.SKCMIXM
