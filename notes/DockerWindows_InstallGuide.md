ref: https://docs.microsoft.com/en-us/windows/wsl/install-win10

# Simplified Installation for Windows Insiders
Enter this command in the command line you've opened in Admin mode: `wsl.exe --install`  
Restart your machine

# Manual Installation Steps
1. Step 1 - Enable the Windows Subsystem for Linux  
   `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`
2. Step 2 - Check requirements for running WSL 2  
   To update to WSL 2, you must be running Windows 10.
   * For x64 systems: Version 1903 or higher, with Build 18362 or higher.
   * For ARM64 systems: Version 2004 or higher, with Build 19041 or higher.
   * Builds lower than 18362 do not support WSL 2. Use the Windows Update Assistant to update your version of Windows.
3. Step 3 - Enable Virtual Machine feature  
   `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`  
   **Restart** your machine to complete the WSL install and update to WSL 2.
4. Step 4 - Download the Linux kernel update package  
   https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi 
5. Step 5 - Set WSL 2 as your default version  
   `wsl --set-default-version 2``
6. Step 6 - Install your Linux distribution of choice  
   Open the Microsoft Store and select your favorite Linux distribution.
   

