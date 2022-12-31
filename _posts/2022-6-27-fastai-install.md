---
title: Install fastAI on Computer (Linux)
date: 2022-6-27 12:00:00 -500
categories: [tutorial,software]
tags: [fastai,nvidia,linux,install,software]
---
# Materials
* A computer with a NVIDIA graphics card:
    * preferably with 4+ GB VRAM, 32+ GB RAM, and 8+ core CPU
* A portable hard-drive
    * SSD – comfortably in range of 512MB/s or more (fast but somewhat risky in case of data loss)
    * HDD – max 100 MB/s (don’t shake or jostle it, also dirt slow)
* USB drive with 8+ Gb

# Install

## Install via WSL
to be updated

## Install via Virtual Machine
to be updated

## Install Linux (Ubuntu)
1. Format the hard-drive (optional)
2. Download latest Bios
3. Create a system image backup [look into this] => might want to avoid this entirely and just creating a VM
4. format your flash drive
5. download and install Balena etcher
6. download and install Ubuntu 20.4 LTS (or whatever version is available)
7. flash Ubunto ISO onto flashdrive
8. Do shrink volume and create a partition for Ubuntu (at least 20 Gb)
- Trouble shooting:
    1. Delete some files
    2. remove Page Indexer (or whatever tf that file is called)
    3. try defraging and rebooting a few times
9. get into bootloader (by restarting and spamming F12, F2, F1, etc.)
10. Ensure a few settings on your computer:
    * AHCI is enabled
    * Secure Boot enabled
11. blah blah blah install ubuntu according to savvy nick tutorial

## Install NVIDIA Drivers
1. open terminal on ubuntu:
2. 
```bash
sudo apt-get update
sudo apt-get upgrade
```
3. Check to see which NVIDIA drivers to install
    1. type in terminal <https://linuxize.com/post/how-to-nvidia-drivers-on-ubuntu-20-04/>: 
    ```ubuntu-drivers devices```
    2. I got something that looked like this in return: [insert screenshot]
    3. Install the recommended driver, in my case I typed into terminal: `sudo apt install nvidia-driver-510`
    4. Once installed reboot system: `sudo reboot`
4. Install Nvidia drivers: (MAKE SURE YOUR TERMINAL IS FULL SCREEN WHEN DOING THIS)
5. Check Nvidia drivers with `nvidia-smi` <https://forums.fast.ai/t/platform-local-server-ubuntu/65851>
6. `sudo add-apt-repository ppa:graphics-drivers/ppa` <https://phoenixnap.com/kb/install-nvidia-drivers-ubuntu>
7. `ubuntu-drivers devices` <https://phoenixnap.com/kb/install-nvidia-drivers-ubuntu>
8. `sudo ubuntu-drivers autoinstall` (alternatively, you could install an individual driver by replacing autoinstall with the specific driver name, but eh)
9. while the drivers are installing, you should get a window that pops up that asks for MOK authentication – for secure boot
10. click okay
11. create a password
12. sudo reboot
13. follow this: https://documentation.commvault.com/commvault/v11/article?p=118661.htm
14. open up terminal again and verify the drivers are there with `nvidia-smi`

## Install miniconda
1. download miniconda for linux from website
2. navigate to downloads folder using ls and cd
3. `chmod +x [name of miniconda file]`
4. `./[name of miniconda file]`
5. press space and enter and yes a few times
6. close terminal and open up a new one and type in conda to see if works

## Install fastAI
This also helped me avoid bugs with running widgets in jupyter notebook:
1. 
```bash
sudo apt install nodejs
sudo apt install npm
sudo apt install git
```
2. create fastbook
```bash
mkdir repos #(folder can be named anything)
cd repos
git clone https://github.com/fastai/fastbook
cd fastbook
conda env create -f environment.yml
conda activate fastbook
pip install fastbook
```
3. open a new terminal for and type `jupyter-lab`
4. navigate to clean and first notebook
5. monitoring GPU and CPU usage and temps: [GPU should be at or near 100% when running epocs, but shouldn’t exceed 85C <= cooling needed if this occurs]
In a new terminal type in `watch -d -n 0.5 nvidia-smi` <https://unix.stackexchange.com/questions/38560/gpu-usage-monitoring-cuda>
6. open up system info to look at CPU cores
7. Run first 3 things in Jupyter

You’re good to go now.
Note: if your system takes x seconds to run this, you probably need a new computer

## Troubleshooting
**Problem:**
```bash
(base) username:~$ nvidia-smi
Failed to initialize NVML: Driver/library version mismatch
```

**Solution:** ^ you probably need to install one of the nvidia drivers (see [Install NVIDIA Drivers](#install-nvidia-drivers)).

**Problem:** If you get something like this:

```
Some packages could not be installed. This may mean that you have
requested an impossible situation or if you are using the unstable
distribution that some required packages have not yet been created
or been moved out of Incoming.
```
**Solution:** The following information may help to resolve the situation:

```
The following packages have unmet dependencies:
nvidia-driver-470 : Depends: nvidia-kernel-source-470 (= 470.103.01-0ubuntu0.20.04.1) but it is not going to be installed
Depends: libnvidia-extra-470 (= 470.103.01-0ubuntu0.20.04.1) but it is not going to be installed
Recommends: libnvidia-ifr1-470:i386 (= 470.103.01-0ubuntu0.20.04.1)
Recommends: libnvidia-gl-470:i386 (= 470.103.01-0ubuntu0.20.04.1)
E: Unable to correct problems, you have held broken packages.
```

Try this: <https://askubuntu.com/questions/140246/how-do-i-resolve-unmet-dependencies-after-adding-a-ppa>
Or try this: <https://askubuntu.com/questions/1362970/problem-installing-nvidia-driver-on-ubuntu-20-04>