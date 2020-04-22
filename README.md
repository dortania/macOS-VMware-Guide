# VMware AMD Hackintosh

I see that you want to make a macOS VM in VMware on your AMD CPU but have no idea how or you need a macOS virtual machine. You've come to the right place. This guide was written for Windows. It may work in Linux but no guarantees.

## Some important things you need to know

Modern CPUs = Anything made from 2010 and onwards

Make sure that Virtualization/AMD-V is supported by your CPU and is enabled in your BIOS. Modern CPUs will definitely support this, but if you have an older CPU, you may want to double check.

Your CPU also needs to support the SSE4.1 instruction set in order to run macOS Sierra and newer. Modern CPUs will also support this. If you have an older CPU, again you should double check. You can use [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html) to check these if you're not sure. 

![](.gitbook/assets/cpuz_x64_ybu0tpuj8s.png)

Due to VMware's graphics acceleration not being compatible with macOS, you will not have any graphics acceleration in your virtual machine. Things like the Launchpad will be extremely laggy, the Dock will be opaque and the virtual machine will not have multiple monitor support. That means that apps like Final Cut Pro will not work at all on this.

The Mac App Store does work, but it will not work straightaway. You will need to do some tweaking to the virtual machine, which you can find in the "Post Installation Tweaks" page. 

iCloud, iMessage, FaceTime & Siri will not work at all.

Do not update you virtual machine. The AMD kernel is only built for 10.15.0 and you will break your virtual machine if you update it.



