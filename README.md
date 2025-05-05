# myArchLinux
A couple of config files for my archlinux computer

## Desktop Environment
The desktop environment I use for my Archlinux installation is HyDE (https://github.com/HyDE-Project/HyDE)

The installation is described in their wiki, here is just a short summary:
```
pacman -S --needed git base-devel
git clone --depth 1 https://github.com/HyDE-Project/HyDE ~/HyDE
cd ~/HyDE/Scripts
./install.sh
```
---
## Sound Output
the lenovo yoga c930 has some problem with build-in audio output. Here is how to fix it:

### 1. Install Required Firmware
Install SOF firmware and ALSA UCM configuration:
```
sudo pacman -S sof-firmware alsa-ucm-conf
```
### 2. Set the Correct Audio Driver
Create/configure the DSP driver override:
```
sudo nano /etc/modprobe.d/dsp.conf
```
Add this line to the file:
```
options snd-intel-dspcfg dsp_driver=1
```
### 3. Reboot
Apply changes with a full reboot:
```
reboot
```
---
