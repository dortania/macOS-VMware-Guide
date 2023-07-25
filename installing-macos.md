# Installing macOS

Now that we've made the virtual machine, it's time to install macOS onto it. 

Start the virtual machine. 

![](.gitbook/assets/p6-s1.png)

Your virtual machine should start up. If you are greeted by this message, press "No". This is only happening because there's no ISO selected in our virtual DVD drive. 

![](.gitbook/assets/p6-s2.png)

As soon as you see the VMware logo pop up on a black background, immediently hit any key to enter the BIOS. 

![](.gitbook/assets/vmplayer_snf5clngda%20%281%29.png)

![](.gitbook/assets/annotation-2019-03-28-190107.jpg)

Select "EFI VMware Virtual SATA Hard Drive \(2.0\)" and press enter. This is our Catalina installer that we are booting. 

![](.gitbook/assets/annotation-2019-03-28-190257.jpg)

The Apple logo should pop up with a moving status bar, like a real mac. This will take a few minutes to boot, so sit back.

![](.gitbook/assets/annotation-2019-03-28-190550.jpg)

The language prompt will come up. Select your language and continue.

![](.gitbook/assets/annotation-2019-03-28-190949.jpg)

Select "Disk Utility" and press "Continue".

![](.gitbook/assets/p6-s7.png)

Select "VMware Virtual SATA Hard Drive Media" under "Internal" hard drive. 

![](.gitbook/assets/p6-s8.png)

Select "Erase" in Disk Utility. Name your drive whatever you want. I'm naming my drive "Catalina". Change "Format" to `APFS` and press "Erase".

![](.gitbook/assets/p6-s9.png)

Press "Done" and close Disk Utility.

![](.gitbook/assets/p6-s10.png)

Select "Reinstall macOS" and press "Continue".

![](.gitbook/assets/p6-s11.png)

When the installer opens, press "Continue".

![](.gitbook/assets/p6-s12.png)

Agree to the terms and conditions.

![](.gitbook/assets/p6-s13a.png)

![](.gitbook/assets/p6-s13b.png)

Select the hard drive that we erased earlier with Disk Utility and press "Install".

![](.gitbook/assets/p6-s14.png)

Sit back and let it install. This will take about 5 mins, depending on your machine. Keep an eye on the virtual machine since it auto-restarts.

![](.gitbook/assets/p6-s15.png)

If the VM restarts and you get a 'CPU is disabled' error, close the error window, attempt to close the VM window, select 'Power Off' and reopen VMware.

![](.gitbook/assets/p6-s16.png)

Start your VM, enter the BIOS and boot back into the Catalina installer.

![](.gitbook/assets/annotation-2019-03-28-194325.jpg)

Once the installer has booted, click on "Utilities" in the Finder bar and select "Terminal".

![](.gitbook/assets/p6-s18.png)

![](.gitbook/assets/p6-s19.png)

Time to do the pre-install command. Type this command in Terminal \(replacing "Catalina" with whatever you named your hard drive earlier\):`cp -rf /Volumes/CatalinaAMD/System/Library/PrelinkedKernels/prelinkedkernel /Volumes/Catalina/"macOS Install Data"/"Locked Files"/"Boot Files"/`

![](.gitbook/assets/vmplayer_y6wcixpwhx.png)

Reboot the VM via the Apple logo and leave it to install. Do not restart via VMware itself. The installation may take a while.

![](.gitbook/assets/annotation-2019-03-28-204917.jpg)

If the VM restarts and you get a 'CPU is disabled' error, close the error window, attempt to close the VM window, select 'Power Off' and reopen VMware.

![](.gitbook/assets/p6-s22.png)

Reboot the VM back into the BIOS, select the installer and open Terminal once again. Time to do the post-install commands. \(replacing "Catalina" with whatever you named your hard drive earlier\): 

```
cp -rf /Volumes/CatalinaAMD/System/Library/Kernels/kernel /Volumes/Catalina/System/Library/Kernels/  
  
rm -rf /Volumes/Catalina/System/Library/PrelinkedKernels/prelinkedkernel  
  
kextcache -u /Volumes/Catalina/
```

For that last command, this is where the results may differ for some people. If you are stuck on "/Volumes/Catalina locked; waiting for lock", leave the VM alone for up to 5 minutes and it should start.

You may get errors like "Warning: /Volumes/Catalina/AppleInternal/Library/Extensions: No such file or directory" or even really fast scrolling text, like shown on the screenshot below. Ignore those errors, the prelinkedkernel should still rebuild just fine.

If you get a "KernelCache ID" at the end of that, that means that the prelinkedkernel rebuilt succesfully. Sometimes you don't get an ID at the end. That's fine too, macOS does that sometimes. As long as you don't get "Error 107", which means it failed to rebuild the prelinkedkernel.

![](.gitbook/assets/p6-s23.png)

Close Terminal and reboot into your hard drive. The VM should boot into the setup now. Go through the setup process but **DO NOT SIGN IN WITH YOUR APPLE ID**, choose "Set Up Later".

![](.gitbook/assets/p6-s24.png)

If you get a notification about software updates, click "Remind Me Tomorrow".

![](.gitbook/assets/p6-s25.png)

You've successfully installed macOS in a virtual machine. Time to install VMware Tools onto it.

