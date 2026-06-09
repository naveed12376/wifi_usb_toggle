# Windows Device Toggle (Wi-Fi + USB Control)

A lightweight Windows utility that allows you to quickly **enable or disable Wi-Fi and USB storage devices** using simple batch scripts.

No installation, dependencies, or additional software are required.

---

## Features

* Enable or disable Wi-Fi with a single click
* Enable or disable USB storage access
* No installation required
* Lightweight and portable
* Supports desktop shortcuts and keyboard hotkeys
* Useful for automation, security, and quick device management

---

## Project Structure

```text
files/
├── on.bat      # Enable Wi-Fi and USB storage
├── off.bat     # Disable Wi-Fi and USB storage
└── README.md
```

---

## How It Works

The scripts perform two actions:

### Wi-Fi Control

Enable Wi-Fi:

```cmd
netsh interface set interface "Wi-Fi" admin=enable
```

Disable Wi-Fi:

```cmd
netsh interface set interface "Wi-Fi" admin=disable
```

### USB Storage Control

Enable USB storage:

```cmd
reg add HKLM\SYSTEM\CurrentControlSet\Services\USBSTOR /v Start /t REG_DWORD /d 3 /f
```

Disable USB storage:

```cmd
reg add HKLM\SYSTEM\CurrentControlSet\Services\USBSTOR /v Start /t REG_DWORD /d 4 /f
```

---

## Usage

### Method 1 – Run Directly

1. Open the `files` folder.
2. Right-click `on.bat` or `off.bat`.
3. Select **Run as Administrator**.

---

## Create Desktop Shortcuts (Recommended)

### Step 1 – Create a Shortcut

1. Right-click the batch file.
2. Select **Create Shortcut**.
3. Move the shortcut to the Desktop (optional).

### Step 2 – Always Run as Administrator

1. Right-click the shortcut.
2. Select **Properties**.
3. Click **Advanced**.
4. Check:

```text
✓ Run as Administrator
```

5. Click **OK** and **Apply**.

### Step 3 – Assign a Keyboard Shortcut

1. Open shortcut **Properties**.
2. Select the **Shortcut** tab.
3. Click the **Shortcut Key** field.
4. Press your preferred key combination.

Example:

```text
Ctrl + Alt + O
```

5. Click **Apply**.

You can now toggle Wi-Fi and USB access instantly using a keyboard shortcut.

---

## Customizing the Wi-Fi Adapter Name

The scripts assume your wireless adapter is named:

```text
Wi-Fi
```

Some systems may use a different name.

To view available interfaces:

```cmd
netsh interface show interface
```

If necessary, update the scripts:

```cmd
netsh interface set interface "YOUR_ADAPTER_NAME" admin=enable
netsh interface set interface "YOUR_ADAPTER_NAME" admin=disable
```

---

## Administrator Privileges Required

These scripts modify:

* Network adapter status
* Windows Registry settings

Because of this, they **must be run with Administrator privileges**.

Without elevated permissions, the commands will fail.

---

## USB Storage Behavior

| Registry Value | Result               |
| -------------- | -------------------- |
| 3              | USB Storage Enabled  |
| 4              | USB Storage Disabled |

> Note: Some systems may require a restart or device reconnect for changes to take full effect.

---

## Use Cases

This project can be useful for:

* Quick device management
* Temporary USB access restrictions
* Productivity workflows
* Classroom and lab environments
* Automation experiments
* Learning Windows batch scripting
* Learning Windows Registry management

---

## Disclaimer

This project modifies Windows network and registry settings. Use it responsibly and ensure you understand the effect of the commands before deploying in production or shared environments.

---

## License

Free to use, modify, and distribute.


## Keywords

Windows WiFi Toggle, Windows USB Control, Disable USB Storage Windows,
Enable Disable WiFi Windows, USBSTOR, Windows Batch Script,
Network Adapter Control, USB Access Control, Windows Automation,
CMD Script, Windows Administration, Device Management

## Author

Developed and maintained by Naveed.

GitHub: https://github.com/naveed12376
