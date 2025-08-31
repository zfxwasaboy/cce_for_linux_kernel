cce_for_linux_kernel_x86_64.sh - CCE (Compiled Code Extractor) for linux kernel on x86_64 architecture
====

cce_for_linux_kernel_x86_64.sh
--
A lightweight script-level compiled code extractor (CCE) for the Linux kernel operates through compilation dependency mechanisms to capture compiled files.


# ✨ Features
- **Precise Code Extraction**: Traces compilation dependency and captures all compiled files within the specified directory.
- **Zero Installation**: Download, unzip, and run immediately.
- **Support Recompiling**: NO.

# ✳️ System Requirements
- **OS**: Linux (Ubuntu, CentOS, Fedora, Red Hat)
- **Architecture**: x86_64
- **Build Systems**: Make, Autotools, CMake, and most common build processes
- **Dependencies**: None
  
# 🚀Quick Start

- **Download and Exact**
```
git clone git@github.com:zfxwasaboy/cce_for_linux_kernel.git
```
`or`
```
https://github.com/zfxwasaboy/ecc_for_linux_kernel > Code > Download ZIP > ecc_for_linux_kernel-main.zip
unzip ecc_for_linux_kernel-main.zip
```

- **Basic Usage**
```
./cce_for_linux_kernel_x86_64.sh
xx@xx-vb:~/Downloads/linux$ ./cce_for_linux_kernel_x86_64.sh all "" "make distclean" "make menuconfig;make -j4"^C
xx@xx-vb:~/Downloads/linux$ ./cce_for_linux_kernel_x86_64.sh 
./cce_for_linux_kernel_x86_64.sh all         <cce_env_setting> <cce_clean> <cce_compile>    Generate depfile and parse depfile
./cce_for_linux_kernel_x86_64.sh gen_depfile <cce_env_setting> <cce_clean> <cce_compile>    Generate depfile
./cce_for_linux_kernel_x86_64.sh parse                                                      Parse depfile,output DIR is out.tmp, time logs at log.tmp
./cce_for_linux_kernel_x86_64.sh clear                                                      Clear installed flags and cce generated temporary files and out.tmp
./cce_for_linux_kernel_x86_64.sh -v                                                         Show version and details about this software

<cce_...> parameters example:
  "" "make distclean" "make menuconfig;make -j4"                                               For x86 case
  "export ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu-" "make clean" "make defconfig;make -j4"  For arm64 case

```

- **Example for extracting linux for x86 architecture**

`run command for x86`:
```
./cce_for_linux_kernel_x86_64.sh all "" "make distclean" "make menuconfig;make -j4"
```

then `select` menuconfig and `exit` to continue

`Check Outputs`:
```
arch/x86/kernel/apic/x2apic_uv_x.c
arch/x86/kernel/x86_init.c
arch/x86/kvm/x86.c
arch/x86/xen/xen-asm.S
arch/x86/kvm/xen.c
arch/x86/kernel/fpu/xstate.c
scripts/kconfig/lxdialog/yesno.c
arch/x86/kernel/cpu/zhaoxin.c
== output dir: out.tmp logfile: log.tmp ==
xx@xx-vb:~/Downloads/linux$ du out.tmp/ -sh
37M	out.tmp/
xx@xx-vb:~/Downloads/linux$ cat log.tmp 
== Starting compile at 2025-08-31 10:39:37 ==
== Ending   compile at 2025-08-31 10:41:30 ==
== Starting sort dep at 2025-08-31 10:41:30 ==
== Ending   sort dep at 2025-08-31 10:41:31 ==
== Starting parse at 2025-08-31 10:41:31 ==
== Ending   parse at 2025-08-31 10:42:29 ==
```

# 📜 License && Support

- **License**: MIT
- **Email**: zfxwasaboy@outlook.com
- **[The Recompilation-Supported CCE](https://github.com/zfxwasaboy/cce)**: Another CCE(Compiled Code Exactor) with broader applicability that supports recompilation





