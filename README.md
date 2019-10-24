# VMware AMD Hackintosh

I see that you want to make a macOS VM in VMware on your AMD CPU but have no idea how or you need a macOS virtual machine. You've come to the right place. This guide was written for Windows. It may work in Linux but no guarantees.

## Some tips to remember:

#### Make sure that Virtualization/AMD-V is supported by your CPU and is enabled in your BIOS. CPUs made from around 2006 or newer should supports this but always good to check.

#### Your CPU also needs to support the SSE4.1 instruction set in order to run Mojave. CPUs made from around 2009 or newer should support this but like I said before, always good to check.

#### You can use [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html) to check if you're not sure. 

![](.gitbook/assets/cpuz_x64_ybu0tpuj8s.png)

#### Due to VMware's graphics acceleration not being compatible with macOS, you will NOT have any graphics acceleration in your virtual machine. Things like the Launchpad will be extremely laggy, the Dock will be opaque and the virtual machine will not have multiple monitor support.

#### Apple's online services \(App Store, iCloud, iMessage, FaceTime & Siri\) will not work in your virtual machine.

#### Do not update you virtual machine. The AMD kernel is only built for 10.14.3 and you will break your virtual machine if you update it.



