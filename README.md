# RT-Thread Applications SDK

This is the Software Development Kit of RT-Thread. You can build your own applications independently just like what you do on Linux.

There are GCC compilers using newlib that adapted for RT-Thread. C/C++ runtime is supported except C++ exceptions.

We supply some examples so you can have a quick look of this SDK.

### Configure of RT-Thread

The Newlib that we supply is adapted for RT-Thread using syscalls. So RT-Thread should support syscalls. You can set `RT_USING_SYSCALLS` on in KConfig. The location is listed following:

```text
Symbol: RT_USING_SYSCALLS [=y]
Type  : boolean
Prompt: Using system call layer
  Location:
(1) -> RT-Thread Components
  Defined at ../../../components/syscalls/Kconfig:1
  Depends on: ARCH_ARM_CORTEX_M7 [=y] && RT_USING_HEAP [=y]
  Selects: RT_USING_DFS [=y] && RT_USING_LIBC [=y]
```

### How to build

We use Makefile to build applications. Specificed dependency rules is defined in `SDK/Makefile.common`. You can include this file in your own `Makefile` and assign the source file that should be compiled and the target file that should be built. The target file should use `.mo` as extension. 

You can get more information through example Makefiles.

### How to run

The application is RT-Thread's dlmodule. It should be stored in file system and run in MSH.

For example, if there was one application called `app.mo` and it was stored in path `/hello/world`, you should type `/hello/world/app.mo` in MSH then press Enter key to run it.