# Installing macOS

Now that we've made the virtual machine, it's time to install macOS onto it. 

Select `Power on this virtual machine`. 

![](.gitbook/assets/annotation-2019-03-28-185310.jpg)

Your virtual machine should start up. If you are greeted by this message, press "No". This is only happening because there's no ISO selected in our virtual DVD drive. 

![](.gitbook/assets/annotation-2019-03-28-184753.jpg)

As soon as you see the VMware logo pop up on a black background, immediently hit any key to enter the BIOS. 

![](.gitbook/assets/vmplayer_snf5clngda%20%281%29.png)

![](.gitbook/assets/annotation-2019-03-28-190107.jpg)

Select "EFI VMware Virtual SATA Hard Drive \(2.0\)" and press enter. This is our Mojave installer that we are booting. 

![](.gitbook/assets/annotation-2019-03-28-190257.jpg)

The Apple logo should pop up with a moving status bar, like a real mac. This will take a few minutes to boot, so sit back.

![](.gitbook/assets/annotation-2019-03-28-190550.jpg)

The language prompt will come up. Select your language and continue.

![](.gitbook/assets/annotation-2019-03-28-190949.jpg)

Select "Disk Utility" and press "Continue".

![](.gitbook/assets/annotation-2019-03-28-191243.jpg)

Select "VMware Virtual SATA Hard Drive Media" under "Internal" hard drive. 

![](.gitbook/assets/annotation-2019-03-28-191707.jpg)

Select "Erase" in Disk Utility. Name your drive whatever you want. I'm naming my drive "Mojave". Change "Format" to `APFS` and press "Erase".

![](.gitbook/assets/annotation-2019-03-28-192221.jpg)

Press "Done" and close Disk Utility.

![](.gitbook/assets/annotation-2019-03-28-192357.jpg)

Select "Reinstall macOS" and press "Continue".

![](.gitbook/assets/annotation-2019-03-28-192808.jpg)

When the installer opens, press "Continue".

![](.gitbook/assets/annotation-2019-03-28-192906.jpg)

Agree to the terms and conditions.

![](.gitbook/assets/annotation-2019-03-28-193038.jpg)

![](.gitbook/assets/annotation-2019-03-28-193113.jpg)

Select the hard drive that we erased earlier with Disk Utility and press "Install".

![](.gitbook/assets/annotation-2019-03-28-193617.jpg)

Sit back and let it install. This will take about 5 mins, depending on your machine. Keep an eye on the virtual machine since it auto-restarts.

![](.gitbook/assets/annotation-2019-03-28-193658.jpg)

If it restarts and you get a 'CPU is disabled' error, attempt to close the VM window, select 'Power Off', reopen VMware.

![](.gitbook/assets/vmplayer_4m0ekxofcu.png)

Start your VM, enter the BIOS and boot back into the Mojave installer.

![](.gitbook/assets/annotation-2019-03-28-194325.jpg)

Once the installer has booted, click on "Utilities" in the Finder bar and select "Terminal".

![](.gitbook/assets/annotation-2019-03-28-194511.jpg)

![](.gitbook/assets/annotation-2019-03-28-194809.jpg)

Time to do the pre-install commands. Type these commands in Terminal \(replacing "Mojave" with whatever you named your hard drive earlier\): `cp -rf /Volumes/MojaveAMD/System/Library/PrelinkedKernels/prelinkedkernel /Volumes/Mojave/macOS\ Install\ Data/Locked\ Files/Boot\ Files/  
sed -i '' 's/auth-//g' /Volumes/Mojave/macOS\ Install\ Data/Locked\ Files/Boot\ Files/com.apple.Boot.plist` 

Reboot the virtual machine and boot to the BIOS. Select "Enter Setup".

![](.gitbook/assets/vmplayer_no8g7heuyd.png)

Select "Configure boot options".

![](.gitbook/assets/vmplayer_f6t7yuddrs.png)

Select "Delete boot option".

![](.gitbook/assets/vmplayer_xvgvt5mql1.png)

Press Enter to the box next to "Mac OS X" and select "Commit changes and exit".

![](.gitbook/assets/vmplayer_c2y2a407sn.png)

Go back into "Configure boot options"

![](.gitbook/assets/vmplayer_f6t7yuddrs.png)

Select "Add boot option".

![](.gitbook/assets/vmplayer_bjlf7h00cu.png)

Choose the name of your partition \("Mojave" in my case\).

![](.gitbook/assets/vmplayer_vj4vv7u1tb.png)

Select "macOS Install Data".

![](.gitbook/assets/vmplayer_43dexf8srv.png)

Select "Locked Files"

![](.gitbook/assets/vmplayer_1zx5kx2gl3.png)

Select "Boot Files"

![](.gitbook/assets/vmplayer_byityctwib.png)

Select "boot.efi"

![](.gitbook/assets/vmplayer_2s5bnf33bs.png)

Select "Input the description" and type "Mac OS X". Select "Commit changes and exit".

![](.gitbook/assets/vmplayer_ceggfkfbxy.png)

Select "Exit the Boot Maintenance Manager".

![](.gitbook/assets/vmplayer_f2g768uolf.png)

Select "Mac OS X" and leave it to install. This may take a while.

![](.gitbook/assets/vmplayer_ydvnqgebfl.png)

![](.gitbook/assets/annotation-2019-03-28-204917.jpg)

If you get this error after installation, press "OK" to restart the VM.

![](.gitbook/assets/vmplayer_jnuhdq3das.png)

When the VM has rebooted, boot back into the installer and open Terminal once again. Time to do the post-install commands. \(replacing "Mojave" with whatever you named your hard drive earlier\): 

`cp -rf /Volumes/MojaveAMD/System/Library/Kernels/kernel /Volumes/Mojave/System/Library/Kernels/  
rm -rf /Volumes/Mojave/System/Library/PrelinkedKernels/prelinkedkernel  
kextcache -u /Volumes/Mojave/`

If you get a "KernelCache ID" at the end of that, that means that the prelinkedkernel rebuilt succesfully. Sometimes you don't get anything at the end. That's fine too, macOS does that sometimes. As long as you don't get "Error 107", which means you've done something wrong.

![](.gitbook/assets/vmplayer_73oymvwfqm.png)

Close Terminal and reboot into your hard drive. You should get into the setup now.

![](.gitbook/assets/vmplayer_zqdglrynm9.png)

Go through the setup process but **DO NOT SIGN IN WITH YOUR APPLE ID**, choose "Set Up Later".

![](.gitbook/assets/vmplayer_tdt9ojllnc.png)

You've successfully installed macOS in a virtual machine. Time to install VMware Tools onto it.

