# Apply the blog [Writing a Simple Linux Kernel Module](https://blog.sourcerer.io/writing-a-simple-linux-kernel-module-d9dc3762c234) on archlinux

### 1. build-essential on archlinux
The package build-essential is a set of packages that you need in order the compile software in Ubuntu or Debian.  
For archlinux run this command: `sudo pacman -S base-devel`  
You may also skip this step if you already have them installed.

### 2. Package [linux-headers](https://archlinux.org/packages/core/x86_64/linux-headers/) on archlinux
Use `uname -r` to check your current kernel version.  
If you are running on an old kerbel version, an [archived linux-headers](https://archive.archlinux.org/packages/l/linux-headers/) should be downloaded and installed.  
Then install the matched linux-headers manually via `pacman -U /path/to/package`  

### 3. Compiling
When compiling this kernel module, a correct GCC version is also required.  
Use `cat /proc/version` to [obtain the corresponding GCC version](https://www.osetc.com/en/how-to-know-the-gcc-version-used-to-compile-linux-kernel-on-linux.html).  
Then `downgrade gcc gcc-libs` to that version.  
Finally, you may execute the `make && make test`

### 4. /linux/arch/x86/lib/cache-smp.c
From https://github.com/torvalds/linux/blob/master/arch/x86/lib/cache-smp.c  
