This is a bash script that extracts a thumbnail from an APK file using aapt.
The PKGBUILD generates a thumbnailer entry so file managers can automatically
and seamlessly use the script.

# Gnome's sandbox

there's an issue with nautilus (Gnome's "Files"), it currently sandbox
thumbnailers and limits their filesystem access down to a predefied set set of
paths. so depending on where `aapt` is installed, the thumbnailer may or may
not work. the aur package `android-sdk-build-tools` for example installs `aapt`
under `/opts`, which is restricted by the sandbox, so if you are using that,
the thumbnailer won't work

# Scalable thumbnails

Modern android apps use scalable graphics written in xml, these require extra
parsing after being extracted, which the script doesn't support

# Future Possibilities

At some point i might re-implement this in java or kotlin, using whatever
algorithm aapt is using to extract thumbnail information. it will be a fun
opportuity to learn about android's packaging format.
