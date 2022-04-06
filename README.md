# My_ArchLinux_Install
This is a complete Guide to install Arch linux from scratch.
I have created various scripts to install Arch linux.


Once completed the Arch linux will look like below.

# ScreenShots
![opnebox](https://user-images.githubusercontent.com/23277835/161943850-7bb9e00c-730a-4477-b0a2-81ba1d226383.gif)
# Features
<a>
  <img src="https://user-images.githubusercontent.com/23277835/161968394-18549645-07da-4476-b0ea-b2149ea70943.jpg" alt="minimal" align="right" width="600px"/>
</a>

- **Window Manager**               • [Openbox](https://www.youtube.com/watch?v=r5HzpWK7SBY) :art: 4 modes!
- **Shell**                        • [Zsh](https://www.zsh.org) :shell: with [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh) framework!
- **Terminal**                     • [kitty](https://github.com/kovidgoyal/kitty)
- **Openbox Menu**                 • [obmenu-generator](https://github.com/trizen/obmenu-generator)
- **Panel**                        • [Tint2](https://gitlab.com/o9000/tint2) :shaved_ice: material icons font!
- **Compositor**                   • [Picom](https://github.com/yshui/picom) :doughnut: rounded corners!
- **Notify Daemon**                • [Dunst](https://github.com/dunst-project/dunst) :leaves: minimalism!
- **Application Launcher**         • [Rofi](https://github.com/adi1090x/rofi) :rocket: blazing fast!
- **File Manager**                 • [Thunar](https://github.com/xfce-mirror/thunar) :bookmark: customized sidebar!
- **Music Player**                 • [Spotify](https://github.com/owl4ce/spicetify-themes/tree/new/Dribbblish#eyecandy) # THEMED
- **GUI Basic-IDE**                • [Geany - The Flyweight IDE](https://www.geany.org)

<details>
  <summary><strong>Audio</strong></summary>
  - Currently the script uses pulse audio. Pipewire will be implemented in the near future.
  - Pulse effects are also installe as a flatpak for cusotmization
  - Spotify is used as the default Music player
  
</details>

<details>
  <summary><strong>Flatpak,AppImages Discover</strong></summary>
  - This supports flatpak, App images for non essential packages(Packages that do not break the install)  and Discover is used to manage the faltpaks.
  
</details>

<details>
  <summary><strong>Auto Cpu Freq</strong></summary>
  - This is enabled by default and can be changed later
  
</details>

<details>
  <summary><strong>Backups</strong></summary>
  - Timeshift backups are enabled by default and accesible from grub
  - snapper is also installed but not configured. can be used if you so choose.
  
</details>

<details>
  <summary><strong>Gaming</strong></summary>
  - Preinstalled steam,lutris and mangohud
  
</details>

<details>
  <summary><strong>BTRFS File System</strong></summary>

- **Features:**
    - BTRFS File system allows for live snapshots. [Learn More](https://github.com/smsriharsha/ArchBaseInstall/blob/main/My_BTRFS.md)
    - It takes up less storage for those snapshots than ext4
    - These snapshots can be booted from grub in case of errors.
</details>
<details>
  <summary><strong>Swap</strong></summary>

  - A swap partition is created based on the requirement.
### Why no swap file?
  - Swap partition is created rather than swap files becasue BTRFS does not play well with swap files and throws permission denied errors.

</details>

<details>
  <summary><strong>GPU Drivers</strong></summary>
  The script auto detects the graphics card and installs drivers.
  
  I have tested the code with Nvidia and Intel drivers .

  AMD i have not tested but confident it would work.

  ## Systems with intel integrated and AMD/Nvidia graphics
  If the system has both intel integrated and a graphics card then both the drivers will be installed.

  </details>



# How to Install

## Step 1

<details>
  <summary><strong>Installaing Base</strong></summary>
  Go to https://github.com/smsriharsha/ArchBaseInstall
 to install the Arch linux base.

 # ArchBase Install Script
 This is a simple Arch install script with only one command to run and a few questions to ans.

 This script is made with minimal install in mind. Less bloat.

 After the script completes the neofetch results in just 130 mb of ram usage.

 This script is made for imtermediate users.  

 To install a Desktop environment Please visit 
https://github.com/smsriharsha/OpenboxInstall.git.


# Features

<details>
  <summary><strong>Ranking mirros</strong></summary>
  Arch linux has many mirrors and ranking these is important. The script selects 6 mirrors based on the speed of the mirrors.
</details>
<details>
  <summary><strong>BTRFS File System</strong></summary>

- **Features:**
    - BTRFS File system allows for live snapshots. [Learn More](https://github.com/smsriharsha/ArchBaseInstall/blob/main/My_BTRFS.md)
    - It takes up less storage for those snapshots than ext4
    - These snapshots can be booted from grub in case of errors.
</details>
<details>
  <summary><strong>Swap</strong></summary>

  - A swap partition is created based on the requirement.
### Why no swap file?
  - Swap partition is created rather than swap files becasue BTRFS does not play well with swap files and throws permission denied errors.

</details>

<details>
  <summary><strong>GPU Drivers</strong></summary>
  The script auto detects the graphics card and installs drivers.
  
  I have tested the code with Nvidia and Intel drivers .

  AMD i have not tested but confident it would work.

  ## Systems with intel integrated and AMD/Nvidia graphics
  If the system has both intel integrated and a graphics card then both the drivers will be installed.

  # Note:

  If there is no mux switch in the laptop to switch the graphics then this will cause problems during boot up and needs to figured out manually by setting the display to boot from intel graphics and not nvidia or amd graphics card.

  </details>

  <details>
  <summary><strong>Microcode</strong></summary>
  Intel and amd microcode will be installed automatically
  </details>

<details>
  <summary><strong>Bootloader</strong></summary>
  the script installs grub boot loader by default and systemd boot loader caused me problems with graphics and btrfs.
  </details>
</br>


# How to use
### Download the latest arch linux iso file and boot from it.
```
https://archlinux.org/download/
```
### After boot run
```
pacman -Sy
pacman -S git
```
### Clone the repository from the git
```
git clone https://github.com/smsriharsha/ArchBaseInstall.git
```
### Chnage the working directory into the folder
Check if the scripts have permissions to run. if not use chmod to give permissions.
# Note 
If you are not from india you have to modify the script to set keybord and time to your location. Modify this part of the script in 2_setup.sh

```
line number 36 to 44 in 2_setup.sh
```

### Run the script crusedo.sh
```
./crusedo.sh
```
## Answer few quesitons about the install and done.
### Install the desktop envronment of your choice. 
### My **recommendations** are the end.
</br></br>


# NOTE: 
  
  SYSTEMD BOOT DOESNT WORK.AMD GPU NOT TESTED
  Tested With only integrated gpu and nvidia gpu.

 This script is used to install the base package of the linux system with btrfs file system.
 
 CHANGE THE LANGUGE AND LOCALES BEFORE USING THE SCRIPT
 
 After the install of the script you can continue with the installation of desktop environment or window manager.

# Want to install Arch linux manually ?
Here is my guide https://github.com/smsriharsha/ArchBaseInstall/blob/main/Manual%20install.txt
## Struck somewhere.. here are a few fixes ..
https://github.com/smsriharsha/ArchBaseInstall/blob/main/ArchInstall_Errors_Fixes.txt
# Credits
 
 Chris titus tech
 ```
 https://github.com/ChrisTitusTech/ArchTitus.git
 ```

# Install The below desktop enviroment if you please.
I have a Open Box script to install the GUI.
# Preview
![5_6188198762796549223](https://user-images.githubusercontent.com/23277835/159973528-02b36055-c773-4690-a218-1f4df88c753f.png)

# Credits for dotfiles and pictures
Harry
```
https://github.com/owl4ce
```

## To use a desktop environment use the script in the below link.
```
https://github.com/smsriharsha/KdeInstall.git
```

</details>

</br>

## Step 2

<details>
  <summary><strong>Installaing GUI</strong></summary>
  This includes GUI window manager login manager etc.

  ### TO install the GUI visit https://github.com/smsriharsha/OpenboxInstall

  # OpenboxInstall
This is a simple customizable script to install a new style of desktop enviroment rather your KDEs and Gnomes....

This is a complete desktop environment experince made from openbox.

This is to be installed after the base install of Arch linux.

Here is my repo to install the same.
https://github.com/smsriharsha/ArchBaseInstall.git

The script uses these dot files:
https://github.com/smsriharsha/Openbox_Dotfiles.git

# NOTE:
Most of the Dotfiles and scritps are from various sources and I have made my tweaks to enhance it to my preference.

I have creditted all the creators in the code and in this readme file.

# Features
<details>
  <summary><strong>Packages</strong></summary>
  - Please have a look at the Packages that are being istalled running the script. 
  - Almost all the packages are essential for the working of the environment.
  - Only remove the packages after install complete install.
    </details>

<details>
  <summary><strong>Audio</strong></summary>
  - Currently the script uses pulse audio. Pipewire will be implemented in the near future.
  - Pulse effects are also installe as a flatpak for cusotmization
  - Spotify is used as the default Music player
  
</details>

<details>
  <summary><strong>Flatpak,AppImages Discover</strong></summary>
  - This supports flatpak, App images for non essential packages(Packages that do not break the install)  and Discover is used to manage the faltpaks.
  
</details>

<details>
  <summary><strong>Auto Cpu Freq</strong></summary>
  - This is enabled by default and can be changed later
  
</details>

<details>
  <summary><strong>Backups</strong></summary>
  - Timeshift backups are enabled by default and accesible from grub
  - snapper is also installed but not configured. can be used if you so choose.
  
</details>

<details>
  <summary><strong>Gaming</strong></summary>
  - Preinstalled steam,lutris and mangohud
  
</details>

# Dotfiles
I am using my other git for the Dotfiles
https://github.com/smsriharsha/Openbox_Dotfiles.git

### Here are a few highlights [Learn More](https://github.com/smsriharsha/Openbox_Dotfiles.git)
### Please support the original creator [HERE](https://github.com/owl4ce/dotfiles.git)

- **Window Manager**               • [Openbox](https://www.youtube.com/watch?v=r5HzpWK7SBY) :art: 4 modes!
- **Shell**                        • [Zsh](https://www.zsh.org) :shell: with [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh) framework!
- **Terminal**                     • [kitty](https://github.com/kovidgoyal/kitty)
- **Openbox Menu**                 • [obmenu-generator](https://github.com/trizen/obmenu-generator)
- **Panel**                        • [Tint2](https://gitlab.com/o9000/tint2) :shaved_ice: material icons font!
- **Compositor**                   • [Picom](https://github.com/yshui/picom) :doughnut: rounded corners!
- **Notify Daemon**                • [Dunst](https://github.com/dunst-project/dunst) :leaves: minimalism!
- **Application Launcher**         • [Rofi](https://github.com/adi1090x/rofi) :rocket: blazing fast!
- **File Manager**                 • [Thunar](https://github.com/xfce-mirror/thunar) :bookmark: customized sidebar!
- **Music Player**                 • [Spotify](https://github.com/owl4ce/spicetify-themes/tree/new/Dribbblish#eyecandy) # THEMED
- **GUI Basic-IDE**                • [Geany - The Flyweight IDE](https://www.geany.org)

 ## Screenshot
 
![opnebox](https://user-images.githubusercontent.com/23277835/161943850-7bb9e00c-730a-4477-b0a2-81ba1d226383.gif)


# How to install
## Prerequisites
Install the base system of arch from 

https://github.com/smsriharsha/ArchBaseInstall.git

## Minimum Requirements & Resource Usage
### My test System Specs
- CPU: Dual core intel i5 5300u
- Memory: 12gb ram
- SSD: 64gb.
- GPU: Integrated
- Display : 1920x1080(required)

### Minimum Requirements (My estimate)
- CPU: Dual Code intel i5 4th gen or above
- Memmory : 2gb (min)/ 4gb remommended
- SSD: 64 GB minimum(256 gb remommended)
- GPU: NA
- Display : 1376x768 or 1920x1080 required
- Dual monitor supported.

## Screenshot of resource usage

![2022-04-02-231741_1920x1080_scrot](https://user-images.githubusercontent.com/23277835/161954742-1d0c2298-8133-4b7c-b1e9-f612a59e568e.png)


## Steps to Install.
Clone the Git repo

```
git clone https://github.com/smsriharsha/OpenboxInstall.git
```

Go into the downloaded folder and if not alredy done
```
chmod 777 openbox_install.sh enabling_services.sh
```

Run the openbox_install script
```
./openbox_install.sh
```

switch to root
```
sudo -s
./enabling_services.sh
```

switch back to user and run
```
sudo -s
./theme_config.sh
```
# Known Problems
Webgreeter at the time of Writing this doc has a few probelms and not getting installed properly.

Visit the official git repo for support.(it will work after dependies are correctly istalled).

### My solution:
install it using yay once and also from git repo using git clone once. then it will work.

### SMB client:
Also does not work on the current version in AUR.
Look at my dependecy list to figure of which version works for smb client or any others.
https://github.com/smsriharsha/Openbox_Dotfiles/blob/main/dependencies_versions.txt


# Credits:
This is hands down my favourite dot files package.
I have made only a few tweaks but most of the work belongs to.

HARRY: (https://github.com/owl4ce)

https://github.com/owl4ce/dotfiles.git

Chris titus tech:
This script is a tweaked version of his KDE install script.



</details>

## Done
