# Making the virtual machine

Now that you've installed VMware Unlocker, open up VMware. 

Select "Create a New Virtual Machine".

![](.gitbook/assets/p5-s1.png)

#### This step is for VMware Workstation people only. VMware Player people can skip to the next step

Choose "Typical \(recommended\)"  and press "Next".

![](.gitbook/assets/vmware_2bmnbdwmab.png)

Select "I will install the operating system later".

![](.gitbook/assets/p5-s3.png)

Select "Apple Mac OS X" under `Guest operating system` and choose "macOS 10.15" under `Version`.

![](.gitbook/assets/p5-s4.png)

Under `Virtual machine name:` "macOS 10.15" will automatically be typed in. You can change this if you want but I'll keep it at the default. Don't worry about `Location:` unless you know what you're doing.

![](.gitbook/assets/p5-s5.png)

Under `Maximun disk size (GB):` the default is "40.0". You can change this size if you wish but I'll keep it at the default size. Keep in mind that the OS will be about 15GB, but macOS requires about 25GB of space to install, so don't go lower than that. Don't go crazy with the virtual hard drive size as this file will be stored on our actual hard drive, so make it a reasonable size. Choose `Store virtual disk as a single file` and press "Next".

![](.gitbook/assets/p5-s6.png)

Press "Finish" and your VM should pop up in VMware.

![](.gitbook/assets/p5-s7.png)

Select "Edit virtual machine settings".

![](.gitbook/assets/p5-s8.png)

The `Memory` section should be selected by default and should have 2 GB of RAM entered by default. This is a very low amount of RAM for macOS and will make macOS run very slow. If you have 8 GB of RAM in your PC or more, it is recommended to increase the VM's memory to at least 4 GB \(4096 MB\) which is what I'll be doing.

![VM with 2GB of RAM allocated](.gitbook/assets/p5-s9a.png)

![VM with 4GB of RAM allocated](.gitbook/assets/p5-s9b.png)

Select `Processors` and select `Number of processors:` to "1". Under `Number of cores per processor:` select the amount of cores that you want to allocate to your VM. You want to have minimum 2 cores allocated and maximum however many cores your CPU has. With virtual machines, you need to allocate some resources like RAM and CPU cores to your virtual machine while still keeping enough for your host operating system. 

![VMware Player](.gitbook/assets/p5-s10a.png)

![VMware Workstation](.gitbook/assets/p5-s10b.png)

Press "Add...". Select `Hard Disk` and press "Next". 

![](.gitbook/assets/p5-s11.png)

Select `SATA` and press "Next".

![](.gitbook/assets/p5-s12.png)

Select `Use an existing virtual disk` and press "Next". 

![](.gitbook/assets/p5-s13.png)

Press "Browse..." and select "CatalinaAMD.vmdk" from wherever you downloaded it. Press "Finish" and press "OK".

![](.gitbook/assets/p5-s14.png)

Press "OK" and minimize VMware for the moment.

![](.gitbook/assets/p5-s15.png)

Navigate to `your Documents folder/Virtual Machines/macOS 10.15 (or whatever you named your VM to)` and open `macOS 10.15 (or whatever you named your VM to).vmx` in a text editor. 

Make a new line and add this: `bios.bootDelay = "2000"` \(measured in milliseconds\). This will delay the BIOS boot up time by 2 seconds giving you a chance to get into the UEFI BIOS if you need to \(which we will need to in a minute\).

![](.gitbook/assets/p5-s16.png)

Save the changes. You've now successfully made your virtual machine. Now time to install macOS on it.



