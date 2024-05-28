```shell
$ mkdir testproject
$ cd testproject/
```

```shell
$ meson init
Using "testproject" (name of current directory) as project name.
Using "testproject" (project name) as name of executable to build.
Defaulting to generating a C language project.
Sample project created. To build it run the
following commands:

meson setup builddir
meson compile -C builddir
```

```shell
$ ls
meson.build  testproject.c
```

```shell
$ meson setup build
The Meson build system
Version: 1.4.0
Source dir: /home/schmidh/Gitrepos/meson-build-system/testproject
Build dir: /home/schmidh/Gitrepos/meson-build-system/testproject/build
Build type: native build
Project name: testproject
Project version: 0.1
C compiler for the host machine: cc (gcc 13.2.0 "cc (GCC) 13.2.0")
C linker for the host machine: cc ld.bfd 2.41
Host machine cpu family: x86_64
Host machine cpu: x86_64
Build targets in project: 1

Found ninja-1.11.1 at /usr/bin/ninja
```

```shell
$ meson compile -C build/
INFO: autodetecting backend as ninja
INFO: calculating backend command to run: /usr/bin/ninja -C /home/schmidh/Gitrepos/meson-build-system/testproject/build
ninja: Entering directory `/home/schmidh/Gitrepos/meson-build-system/testproject/build'
[2/2] Linking target testproject
```

```shell
$ ./build/testproject
This is project testproject.
```

```shell
$ meson test -C build/
ninja: Entering directory `/home/schmidh/Gitrepos/meson-build-system/Absolute-Beginner-Guide/testproject/build'
ninja: no work to do.
1/1 basic        OK              0.00s

Ok:                 1
Expected Fail:      0
Fail:               0
Unexpected Pass:    0
Skipped:            0
Timeout:            0

Full log written to /home/schmidh/Gitrepos/meson-build-system/Absolute-Beginner-Guide/testproject/build/meson-logs/testlog.txt
```

```shell
# format all source files
$ ninja -C build/ clang-format
```

```shell
$ meson setup release-build --buildtype release
```

```shell
$ meson compile -C release-build/
```

```shell
$ DESTDIR=/tmp/testproj meson install -C release-build/
ninja: Entering directory `/home/schmidh/Gitrepos/meson-build-system/Absolute-Beginner-Guide/testproject/release-build'
ninja: no work to do.
Installing testproject to /tmp/testproj/usr/local/bin
```
