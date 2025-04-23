# Winget-on-Windows-11-IoT
How to install Winget on Windows 11 IoT

The official documentation is located here: https://learn.microsoft.com/en-us/windows/iot/iot-enterprise/deployment/install-winget-windows-iot

Follow the instructions. If you get this error error:

"C:\Users\xxxx\Downloads\Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle"
Add-AppxPackage : Deployment failed with HRESULT: 0x80073CF3, Package failed updates, dependency or conflict
validation.
Windows cannot install package Microsoft.DesktopAppInstaller_1.26.210.0_x64__8wekyb3d8bbwe because this package
depends on a framework that could not be found. Provide the framework "Microsoft.VCLibs.140.00.UWPDesktop" published
by "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US", with neutral or x64 processor
architecture and minimum version 14.0.33728.0, along with this package to install.
NOTE: For additional information, look for [ActivityId] 39f6ec4c-ae9a-0000-8745-f8399aaedb01 in the Event Log or use
the command line Get-AppPackageLog -ActivityID 39f6ec4c-ae9a-0000-8745-f8399aaedb01
At line:1 char:1
+ Add-AppxPackage -Path "C:\Users\paul\Downloads\Microsoft.DesktopAppIn ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : WriteError: (C:\Users\paul\D...bbwe.msixbundle:String) [Add-AppxPackage], IOException
    + FullyQualifiedErrorId : DeploymentError,Microsoft.Windows.Appx.PackageManager.Commands.AddAppxPackageCommand

PS C:\Users\xxxx\Downloads>

Then use the vclibs file linked in this repo: Microsoft.VCLibs.140.00.UWPDesktop_14.0.33728.0_x64__8wekyb3d8bbwe.Appx
