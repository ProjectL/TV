##Project L

###Logging
------------

Right now, Project L TVs based on Android systems are being logged to Logentries using LogCat to UDP app.

[LogCat to UDP]https://play.google.com/store/apps/details?id=sk.madzik.android.logcatudp
               http://app.loqoo.tv/bEeY9D

In order for the full extent of logcat to push through to our remote logger the logging app must be install as a system app.
The steps to recreate in doing so are as followed:
(Obviously the system must be rooted as are all the systems Project L uses in the field)

```shell
$ su
$ mount ( to check mounts )
$ mount -o remount,rw /system ( this is for {manufaturer: "JLD", model: "S802"} based systems )
$ cp sk.madzik.android.logcatudp-1.apk /system/app

=========

THE ABOVE DOES NOT THE SYSTEMS LOGCAT B/C OF LACK OF PRIVILEGES.
THIS IS BEING WORK OUT AT THE MOMENT.
