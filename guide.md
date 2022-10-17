## Guide: Optimus Manager for hybrid GPU setup (Arch)

*Installing yay - Package Manager*

    sudo pacman -Syyu
    sudo pacman -S yay
    yay -Syu

*Installing Nvidia drivers and Basic compiling tools*

    yay -S nvidia
    yay -S base-devel

*Installing Optimus Manager*

    yay -S optimus-manager optimus-manager-qt

*Disable Bumblebee daemon*

    sudo systemctl disable bumblebeed.service

*Disable Xorg graphic configurations*

    cd  /etc/X11/xorg.conf.d/
    sudo mv 90-mhwd.conf 90-mhwd.conf.bak
    cd ..
    sudo mv nvidia.conf nvidia.conf.bak

<u>*KDE USERS ONLY* </u>
*Changing default configuration of SDDM*

    sudo nano /etc/sddm.conf
    #Comment these two commands by putting # in front of them
    #DisplayCommand
    #DisplayStopCommand

*Reboot and Final Check*

    systemctl status optimus-manager.service

> refer:
> https://archived.forum.manjaro.org/t/guide-install-and-configure-optimus-manager-for-hybrid-gpu-setups-intel-nvidia/92196
