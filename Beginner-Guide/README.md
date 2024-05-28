```shell
$ meson --version
1.4.0
```

```shell
$ ninja --version
1.11.1
```

```shell
$ mkdir testproject
$ cd testproject
```

```shell
$ meson init --name testproject --build
Using "testproject" (project name) as name of executable to build.
Defaulting to generating a C language project.
Sample project created. To build it run the
following commands:

meson setup builddir
meson compile -C builddir

Building...
The Meson build system
Version: 1.4.0
Source dir: /home/schmidh/Gitrepos/meson-build-system/Absolute-Beginner-Guide/testproject
Build dir: /home/schmidh/Gitrepos/meson-build-system/Absolute-Beginner-Guide/testproject/build
Build type: native build
Project name: testproject
Project version: 0.1
C compiler for the host machine: cc (gcc 13.2.0 "cc (GCC) 13.2.0")
C linker for the host machine: cc ld.bfd 2.41
Host machine cpu family: x86_64
Host machine cpu: x86_64
Build targets in project: 1

Found ninja-1.11.1 at /usr/bin/ninja
ninja: Entering directory `build'
[2/2] Linking target testproject
```

```shell
$ build/testproject
This is project testproject.
```

```shell
$ meson compile -C build/
INFO: autodetecting backend as ninja
INFO: calculating backend command to run: /usr/bin/ninja -C /home/schmidh/Gitrepos/meson-build-system/Absolute-Beginner-Guide/testproject/build
ninja: Entering directory `/home/schmidh/Gitrepos/meson-build-system/Absolute-Beginner-Guide/testproject/build'
ninja: no work to do.
```
