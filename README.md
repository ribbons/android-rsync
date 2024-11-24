Android rsync Builds
====================

![Build status](https://github.com/ribbons/android-rsync/workflows/Build/badge.svg)

Build script to cross-compile [rsync](https://rsync.samba.org/) for Android.


Precompiled Binaries
--------------------

armv7a, aarch64, i686 and x86_64 Android binaries compiled under GitHub Actions
are available as release assets from this repository.

There is a JAR release asset containing all of the binaries (renamed to
librsync.so to allow them to be executed from within an Android app).  This is
also [available as a package](https://central.sonatype.com/artifact/com.nerdoftheherd/android-rsync)
for ease of use as a dependency in Android Studio.


Manual Build
------------

* Ensure that the Android NDK is located at `$ANDROID_NDK_HOME` or
  `$ANDROID_HOME/ndk-bundle`.
* Run `./build`


Example Usage
-------------

From an Android app with the published package added as a dependency:

``` kotlin
val libDir = context.applicationInfo.nativeLibraryDir

val args = ArrayList<String>()
args.add("$libDir/librsync.so")
args.add("--version")

val builder = ProcessBuilder(args)
val rsync = builder.start()

val result = rsync.waitFor()
val stdout = rsync.inputStream.bufferedReader().use(BufferedReader::readText)
val stderr = rsync.errorStream.bufferedReader().use(BufferedReader::readText)

Log.d(TAG, "Exit code: $result")
Log.d(TAG, "Standard out: $stdout")
Log.d(TAG, "Standard error: $stderr")
```

For a full example, you can check out the source of my
[Rsync for Tasker](https://github.com/ribbons/TaskerRsync) app.
