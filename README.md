Android rsync Builds
====================

![Build status](https://github.com/ribbons/android-rsync/workflows/Build/badge.svg)

Build script to cross-compile [rsync](https://rsync.samba.org/) for Android.


Precompiled Binaries
--------------------

armv7a, aarch64, i686 and x86_64 Android binaries compiled under GitHub Actions
are available as release assets from this repository.


Manual Build
------------

* Ensure that the Android NDK is located at `$ANDROID_NDK_HOME` or
  `$ANDROID_HOME/ndk-bundle`.
* Run `./build`
