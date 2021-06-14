# CIS-DISA-Windows-Server-2016

This project was created to facilitate the implementation of security criteria based on CIS and DISA.

The components of this project are adapted to a Windows Server 2016 operating system that is not present in any Active Directory domain.

Here is the set of components:
- A "Reg" directory containing the register entries
- A "Backup" directory containing the local group policy template
- A "Powershell" folder
- A "Summary.ds" table summarizing the settings
- A "LGPO.exe" utility

First of all, I invite you to look at the summary table, and advise you to create a backup of your system before starting anything! You could restore your system in case of problems.


## Installation

1) Download the project folder to your C:\ drive.

2) Import the .reg files :

Go to the "Reg" folder, then double click on the "All.reg" file.

3) Open the powershell console with administrator privileges, then run the script ".\V-70639.ps1", and restart your server.

4) Check the NTFS permissions on the "eventvwr.exe" application in the %SystemRoot%\SYSTEM32 path.

5) Open the powershell console with administrator privileges and import the local group policy template :

```
cd C:\CIS-DISA-Windows-Server-2016\
```
```
.\LGPO.exe /g .\Backup\
```
```
gpupdate /force
```

Restart our server, and log in with the administrator account "admin1x8rtm".


## Finally

I am aware that this project is not perfect, so don't hesitate to suggest improvements!
