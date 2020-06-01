# Windows Subsystem for Linux Installation (WSL2)

## Install the Windows Subsystem for Linux

Before installing any Linux distributions on Windows, you must enable the "Windows Subsystem for Linux" optional feature.

Open PowerShell as Administrator and run:

`dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`

To only install WSL 1, you should now restart your machine and move on to Install your Linux distribution of choice, otherwise wait to restart and move on to update to WSL 2.

## Update to WSL 2

To update to WSL 2, you must running **Windows 10 version 2004**, Build 19041 or higher.

### Enable the 'Virtual Machine Platform' optional component

Before installing WSL 2, you must enable the **Virtual Machine Platform** optional feature.

Open PowerShell as Administrator and run:

`dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`

Restart your machine to complete the WSL install and update to WSL 2.

## Updating the WSL 2 Linux kernel

### Download the Linux kernel update package

Please [download the latest WSL2 Linux kernel](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi) update package for x64 machines, and then install the Linux kernel update package.

## Set WSL 2 as your default version

Run the following command in Powershell to set WSL 2 as the default version when installing a new Linux distribution:

`wsl --set-default-version 2`

Now you can open the **Microsoft Store**, select and install your favorite Linux distribution. And use the command `wsl -l -v` to see what you have installed
