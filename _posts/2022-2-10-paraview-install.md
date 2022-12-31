---
title: How to Install Paraview
date: 2022-2-10 12:00:00 -500
categories: [tutorial,software]
tags: [paraview,linux,install,software]
---
# Install
Everything is based off this video: <https://www.youtube.com/watch?v=tWEGjWD8d2M>

**Note: wherever it says 5.10.0, replace that with your version either manually or by hitting the tab button to autocomplete.** 

1. See if you have paraview already installed: open a terminal and type: `which paraview`
- If nothing happens, you don’t have it installed.
- If a file/folder path shows up, then you have it installed. Then type in: `sudo apt-get remove paraview`
**note: if you’re ever typing in the name of something such as an application or folder, try typing in the first few letters and then hitting tab to autocomplete. You might have something installed such as paraview-4.0, which Linux would be able to autofind for you.**
2. Download ParaView: <https://www.paraview.org/download/>
3. 
```
sudo tar -xvzf ~/Downloads/ParaView-5.10.0-MPI-Linux-Python3.9-x86_64.tar.gz -C /opt/
```
- `(optional) cd ../..`
- if you’re on a shared network computer, don’t do this and just remain in `~` directory.
```bash
cd /opt/
```
4. `ls` to check if the file has been installed.
5. Change the name to something more reasonable
```
sudo mv ParaView-5.10.0-MPI-Linux-Python3.9-x86_64 ParaView-5.10
```
6. `ls` to check if file was renamed
7. Add to bashrc file
```bash
sudo gedit ~/.bashrc
```
- copy and paste this to the end of the file: `export PATH=$PATH:/opt/ParaView-5.10/bin/`
- save file
9. Gain terminal access to paraview:
```
sudo ln -s /opt/ParaView-5.10/bin/paraview /usr/bin/paraview
sudo ln -s /opt/ParaView-5.10/lib/paraview-5.10/ /usr/lib/paraview-5.10
```
10. Make a launcher icon:
```bash
sudo gedit /usr/share/applications/paraview.desktop
```
- copy and paste the below and save:
```
[Desktop Entry]
Version=1.0
Name=ParaView 5.10
Exec=paraview
Terminal=false
Icon=/opt/ParaView-5.10/share/icons/hicolor/96×96/apps/paraview.png
Type=Application
x-Ayatana-Desktop-Shortcuts=NewWindow
[NewWindow Shortcut Group]
Name=New Window
Exec=paraview
TargetEnvironment=Unity
```