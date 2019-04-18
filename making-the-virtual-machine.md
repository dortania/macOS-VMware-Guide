---
description: >-
  The rest of these screenshots will come from my host computer or the actual
  macOS VM
---

# Making the virtual machine

Now that you've installed VMware Unlocker, open up VMware. 

#### The 2nd step is for VMware Workstation people only. VMware Player people can skip to the next step

* Select "Create a New Virtual Machine".

![](.gitbook/assets/annotation-2019-03-24-090258.jpg)

* Choose "Typical \(recommended\)"  and press "Next".

![](.gitbook/assets/annotation-2019-03-24-090430.jpg)

* Select "I will install the operating system later".

![](.gitbook/assets/annotation-2019-03-24-090503.jpg)

* Select "Apple Mac OS X" under `Guest operating system` and choose "macOS 10.14" under `Version`.

![](.gitbook/assets/annotation-2019-03-24-090539.jpg)

* Under `Virtual machine name:` "macOS 10.14" will automatically be typed in. You can change this if you want but I'll keep it at the default. Don't worry about `Location:` unless you know what you're doing.

![Your virtual machines will be in your Documents folder.](.gitbook/assets/annotation-2019-03-24-090616.jpg)

* Under `Maximun disk size (GB):` the default is "40.0". You can change this size if you wish but I'll keep it at the default size. Keep in mind that macOS requires about 12GB of space to install, so don't go lower than that. Don't go crazy with the virtual hard drive size as this file will be stored on our actual hard drive, so make it a reasonable size. Choose `Store virtual disk as a single file` and press "Next".

![](.gitbook/assets/annotation-2019-03-24-090734.jpg)

* Press "Finish" and your VM should pop up in VMware.

![](.gitbook/assets/annotation-2019-03-24-090828.jpg)

* Select "Edit virtual machine settings.

![](.gitbook/assets/annotation-2019-03-24-090956.jpg)

* The `Memory` section should be selected by default and should have 2 GB of RAM entered by default. This is a very low amount of RAM for macOS and will make macOS run very slow. If you have 8 GB of RAM in your PC or more, it is recommended to increase the VM's memory to at least 4 GB \(4096 MB\) which is what I'll be doing.

![VM with 2GB of RAM allocated](.gitbook/assets/annotation-2019-03-24-091158.jpg)

![VM with 4GB of RAM allocated](.gitbook/assets/annotation-2019-03-24-092334.jpg)

* Select `Processors` and select `Number of processors:` to "1". Under `Number of cores per processor:` select the amount of cores that you want to allocate to your VM. You want to have minimum 2 cores allocated and maximum however many cores your CPU has. With virtual machines, you need to allocate some resources like RAM and CPU cores to your virtual machine while still keeping enough for your host operating system. 

![VMware Player](.gitbook/assets/annotation-2019-03-24-093651.jpg)

![VMware Workstation](.gitbook/assets/annotation-2019-03-24-093816.jpg)

* Press "Add...". Select `Hard Disk` and press "Next". 

![](.gitbook/assets/annotation-2019-03-24-093931.jpg)

* Select `SATA` and press "Next".

![](.gitbook/assets/annotation-2019-03-24-094029.jpg)

* Select `Use an existing virtual disk` and press "Next". 

![](.gitbook/assets/annotation-2019-03-24-094055.jpg)

* Press "Browse..." and select "MojaveAMD.vmdk" from wherever you downloaded it. Press "Finish" and press "OK".

![Mine is located in D:\](.gitbook/assets/annotation-2019-03-24-094139.jpg)

* Navigate to `your Documents folder/Virtual Machines/macOS 10.14 (or whatever you named your VM to)` and open `macOS 10.14 (or whatever you named your VM to).vmx` in a text editor. 
* Make a new line and add this: `bios.bootDelay = "2000"` \(measured in milliseconds\). This will delay the BIOS boot up time by 2 seconds giving you a chance to get into the UEFI BIOS if you need to \(which we will need to in a minute\).

![](.gitbook/assets/annotation-2019-03-23-235046.png)

#### This step is for Ryzen users only. If you have an FX or A-Series APU, skip this step.

* Make a new line and add this: `cpuid.1.eax = "0000:0000:0000:0001:0000:0110:1010:0101"`

![](.gitbook/assets/annotation-2019-03-23-235257.png)

* Save the changes. You've now successfully made your virtual machine. Now time to install macOS on it.



