# wifi_usb_toggle
Windows batch scripts to enable/disable Wi-Fi adapters and USB storage access using netsh and Windows Registry commands. Useful for quick system control and automation tasks.

Windows Device Toggle (Wi-Fi + USB Control)

This repository provides two simple batch scripts to quickly enable or disable Wi-Fi and USB storage on Windows.

No installation is required — just run the scripts with administrator access.

📁 Project Structure
📁 files
├── on.bat
├── off.bat
|___ readme.txt
⚙️ What It Does

These scripts control:

Wi-Fi adapter state (enable/disable)
USB storage access via Windows Registry
Internal Commands Used:
netsh interface set interface "Wi-Fi" admin=enable
netsh interface set interface "Wi-Fi" admin=disable

reg add HKLM\SYSTEM\CurrentControlSet\Services\USBSTOR /v Start /t REG_DWORD /d 3 /f
reg add HKLM\SYSTEM\CurrentControlSet\Services\USBSTOR /v Start /t REG_DWORD /d 4 /f
🚀 How to Use (Recommended Method)
1. Run the Scripts Manually (Basic Method)
Go to files/ folder
Right-click on.bat or off.bat
Select Run as Administrator
⚡ Create Desktop Shortcut (Recommended for Fast Access)
Step 1: Create Shortcut
Right-click on.bat or off.bat
Click Create Shortcut
Move the shortcut to Desktop (optional)
Step 2: Run as Administrator Always
Right-click the shortcut
Click Properties
Click Advanced
Enable:
✔ Run as administrator
Step 3: Assign Keyboard Shortcut (Hotkey)
Open shortcut Properties
Click the Shortcut Key field
Press your desired key combo (example: Ctrl + Alt + O)
Click Apply

Now you can toggle Wi-Fi + USB instantly using keyboard shortcuts.

🎨 Optional: Change Icon
Right-click shortcut → Properties
Click Change Icon
Choose any .ico file or system icon
Apply changes
⚠️ Important Notes
1. Wi-Fi Adapter Name May Differ

If your system does not use "Wi-Fi" as adapter name, you must change it manually.

Check your adapter name using:

netsh interface show interface

Then update this line in the script:

netsh interface set interface "YOUR_ADAPTER_NAME" admin=enable
2. Administrator Required

These scripts modify system settings:

Network adapter state
Windows registry (USB storage control)

Always run as Administrator, or they will fail.

3. USB Effect
USBSTOR = 3 → USB enabled
USBSTOR = 4 → USB disabled

A restart may sometimes be required for full effect.

📌 Purpose

This project is meant for:

Quick system control
Automation practice
Learning Windows batch + registry commands
