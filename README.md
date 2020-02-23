Android Dropbear Builds
=======================

![Build status](https://github.com/ribbons/android-rsync/workflows/Build/badge.svg)

Build script to cross-compile [rsync](https://rsync.samba.org/) for Android.


Precompiled Binaries
--------------------

armv7a and aarch64 binaries compiled under GitHub Actions are available as
release assets from this repository.


Manual Build
------------

* Ensure that the Android NDK is located at `$ANDROID_NDK_HOME` or
  `$ANDROID_HOME/ndk-bundle`.
* Download and unpack the latest rsync source into a subfolder named `rsync`.
* Run `./build`
