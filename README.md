# Mediatek IMS

* This repository provides a prebuilt IMS (IP Multimedia Subsystem) package for Mediatek devices, rebuilt and adapted to work seamlessly with **AOSP 16** and newer.
* The aim is to eliminate the dependency on scattered Mediatek ELF blobs and tightly-coupled proprietary components that frequently break with each AOSP release.

## ✨ Features

- ✅ **Unified IMS Package**: Includes all necessary Mediatek IMS framework components in a single APK.
- ✅ **Commonized IMS**: If your stock blobs are from VNDK S & above vendor, this ims package will work for your seamlessly.
- ✅ **No External Blobs Required**: Eliminates the need for individual ELF blobs like `libmtk_vt_service.so, vtservice`, etc.
- ✅ **AOSP 16+ Compatible**: Rebuilt and tested against AOSP 16 QPR2 sources.
- ✅ **Plug-and-Play**: Just include the `ims.mk` Makefile — no more hacks or blob chases.

## 📦 How it works?

* Basically the mtk-ims is built on AOSP codebase with all dependencies and framework included in same APK :).

## 🚀 Integration Guide

1. **Clone this repository to your AOSP source tree**,:

```
git clone https://github.com/techyminati/android_vendor_mediatek_ims vendor/mediatek/ims/
```

2. **In your device-specific product makefile**, inherit the IMS configuration:

```
$(call inherit-product, vendor/mediatek/ims/ims.mk)
```

3. **Build AOSP** as usual. The prebuilt APK, overlays & properties will be included automatically.

## 🛠️ Build Behavior

* The included APK is signed and ready to use.
* No need to build additional Mediatek-specific services or framework jars.
* IMS registration, VoLTE, and VoWiFi functionalities (where supported) should work out-of-the-box. [ViLTE may/may not work]

## ❗Disclaimer

* This project is intended for use by developers porting AOSP to Mediatek devices.
* Tested on AOSP 16 QPR2+. Compatibility with earlier/later versions may require additional patches.
* IMS/VoLTE features may depend on proper carrier and modem configurations.

## 📄 License

This repository is licensed under Apache License 2.0

## About
Maintained by [Aryan Sinha](https://github.com/techyminati)
