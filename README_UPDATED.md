# 🛠️ Install WinGet on Windows 11 IoT Enterprise (LTSC)

This guide walks you through installing the **Windows Package Manager (WinGet)** on **Windows 11 IoT Enterprise**, which lacks the Microsoft Store by default.

> 📄 **Official Documentation**:  
> [Install WinGet on Windows IoT Enterprise](https://learn.microsoft.com/en-us/windows/iot/iot-enterprise/deployment/install-winget-windows-iot)

---

## ⚠️ Common Installation Error

When trying to install the `.msixbundle`, you may see this error:

```
Add-AppxPackage : Deployment failed with HRESULT: 0x80073CF3, Package failed updates, dependency or conflict validation.

Windows cannot install package Microsoft.DesktopAppInstaller_1.26.210.0_x64__8wekyb3d8bbwe because this package
depends on a framework that could not be found: "Microsoft.VCLibs.140.00.UWPDesktop"
```

---

## ✅ Fix: Install Required VC++ Dependency

Download and install this required dependency **before** installing WinGet:

**➡️ [Microsoft.VCLibs.140.00.UWPDesktop_14.0.33728.0_x64__8wekyb3d8bbwe.Appx](https://github.com/paulerrr/Winget-on-Windows-11-IoT/blob/main/Microsoft.VCLibs.140.00.UWPDesktop_14.0.33728.0_x64__8wekyb3d8bbwe.Appx?raw=true)**

Then re-run your `Add-AppxPackage` command:

```powershell
Add-AppxPackage -Path "C:\Path\To\Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle"
```

---

## 📝 Notes

- Always run **PowerShell as Administrator** when installing `.appx` or `.msixbundle` files.
- After installation, `winget` should be available here:
  ```
  C:\Users\<YourUsername>\AppData\Local\Microsoft\WindowsApps
  ```
- If `winget` is not recognized:
  - Restart PowerShell
  - Or reboot the system
