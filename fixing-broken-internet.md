# Fixing Broken Internet

After releasing this guide, people have noticed that copying the modified "IONetworkingFamily" kext from the installer during post-install results in broken internet and unable to add any network services in System Preferences. 

The guide has been updated to fix this problem. The "cp -rf ... IONetworkingFamily.kext ..." has been removed. Reinstall macOS following this guide again. 

Basically, we aren't copying the modified "IONetworkingFamily" kext. Rather, we are leaving the kext that macOS installs for us. 

