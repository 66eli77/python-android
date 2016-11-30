Reference:
    http://code.google.com/p/python-for-android/

./bootstrap.sh
    Downloads Python-2.7.2 source
    patches Python for android
    builds hostpython and hostpgen

./build.sh
    builds python library for android

./package.sh
    creates python_rxx.zip and python_extras_rxx.zip

./pip_install.sh
    install python packages using pip.
    example:
        ./pip_install.sh python-twitter


-------

# Eli's journey

1. I installed the following packages:

```
sudo apt-get install build-essential cpp-4.4 g++-4.4 gcc-4.4-base gcc-4.4 bison flex autoconf automake autotools-dev quilt libcurl3 curl openssh-server ant mercurial filezilla pure-ftpd dpatch texinfo libncurses5-dev libgmp3-dev libmpfr-dev gawk patchutils binutils-dev zlib1g-dev 
```

and

```
sudo apt-get install git-core gnupg gperf libc6-dev x11proto-core-dev libx11-dev libgl1-mesa-dev g++-multilib mingw32 tofrodos python-markdown libxml2-utils xsltproc libreadline-dev libreadline6 ia32-libs-multiarch libzip-dev libzip-dev libzzip-dev libzzip-0-13
```

2. I'm using ubuntu [ubuntu-12.04.3-dvd-i386](http://old-releases.ubuntu.com/releases/releases/12.04/release/ubuntu-12.04.3-dvd-i386.iso) (32-bit)
3. check your gcc version, make sure you are using gcc-4.4, mine defaulted to gcc-4.6. I also changed default to gcov-4.4, g++-4.4.
4. [android-ndk-r7c](http://dl.google.com/android/ndk/android-ndk-r7c-linux-x86.tar.bz2)
5. [andriod-sdk-linux](https://dl.google.com/android/android-sdk_r24.4.1-linux.tgz)
6. the site.py file inside python_extras_27.zip won't work, a work around for now is to replace it with the site.py from android-python27 project.

-------


current status:
    Python build finished, but the necessary bits to build these modules were not found:
    _bsddb             _curses            _curses_panel
    _tkinter           bsddb185           bz2
    dbm                dl                 gdbm
    imageop            linuxaudiodev      nis
    ossaudiodev        readline           sunaudiodev
    To find the necessary bits, look in setup.py in detect_modules() for the module's name.


    Failed to build these modules:
    _ctypes_test       _locale            audioop
    grp                spwd
