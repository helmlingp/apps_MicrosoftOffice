# apps_MicrosoftOffice
A collection of configuration/installation files to deploy Microsoft Office. 
References:
https://docs.microsoft.com/en-us/deployoffice/overview-office-deployment-tool#download-the-installation-files-for-microsoft-365-apps
https://docs.microsoft.com/en-us/deployoffice/admincenter/overview-office-customization-tool
Create configuration file at - https://config.office.com/deploymentsettings

Also included are Visio and Project configurations without Office as well as combinations of Office with Visio and Project.

Use the configuration files to install or re-configure a Office using a similar command line:
`setup.exe /configure Configuration-Office2019ProPlus.xml`

The same configuration files are also used to download the offline installer to an Office\Data subfolder.
See https://docs.microsoft.com/en-us/deployoffice/overview-office-deployment-tool#download-the-installation-files-for-microsoft-365-apps 
Use the following command line example:
`setup.exe /download Configuration-Office2019ProPlus.xml`

Use the Uninstall* configuration files to uninstall
`setup.exe /configure Uninstall-OfficeProPlus2019.xml`

**Deploying with Workspace ONE**
1. Create the configuration files or use the provided configuration file as a template
2. Create a folder and place the Office Deployment Tool and configuration files (install & uninstall) in the folder
3. Download the offline installer using the install configuration file
4. ZIP the contents of the folder
5. Upload as a new application into the WS1 console and provide the following parameters:
   a. Install Command - setup.exe /download Configuration-Office2019ProPlus.xml
   b. Uninstall Command - setup.exe /configure Uninstall-OfficeProPlus2019.xml
   c. set disk space, power and RAM requirements; install context = Device; admin privileges = Yes; reboot exit code = 1641; success exit code = 0;
   d. set when to call install complete = File exists - "C:\Program Files\Microsoft Office\root\Office16\OUTLOOK.EXE"
