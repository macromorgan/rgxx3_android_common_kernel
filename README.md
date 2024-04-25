This is my attempt at using the android-common-kernel on the RGxx3
series from Anbernic. The goal is to eventually have a working AOSP
distro for the device that can use a GKI, a GSI, and passes the VTS
and any other tests. This kernel is still very untested, but it's
based on mainline sources which have been tested.

To build, first repo sync an Android Common Kernel.
https://source.android.com/docs/core/architecture/kernel/android-common

For this branch for the moment I am using the android15-6.6 branch.

To build, copy this directory into your android-kernel directory. So if
you run `repo sync` from /home/user/android-kernel then you would copy
this folder to /home/user/android-kernel/rgxx3.

To build, go into your android-common folder and run the following
commands:

`tools/bazel build //rgxx3:rgxx3_dist`
`tools/bazel run //rgxx3:rgxx3_dist`

Then, copy all the output files into your working android folder into
the correct device/anbernic/rgxx3-kernel/ folder.

`cp -r out/rgxx3/dist/* /path/to/device/anbernic/rgxx3-kernel/.`
