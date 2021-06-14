# CIS-DISA-Windows-Server-2016

This project was created to facilitate the implementation of security criteria based on CIS and DISA.

The components of this project are adapted to a Windows Server 2016 operating system that is not present in any Active Directory domain.

Here is the set of components:
- A "Reg" directory containing the register entries
- A "GpoTemplate" directory containing the local group policy template
- A "Summary.ds" table summarizing the settings
- A "LGPO.exe" utility

First of all, I invite you to look at the summary table, and advise you to create a backup of your system before starting anything! You could restore your system in case of problems.


## Installation

<<<<<<< HEAD
1) Download the project folder to your C:\ drive.
=======
First step, download this github project to your C:\ drive.
>>>>>>> 7106a0a16a985339c36d45dfa60e1c823c9fdb26


2) Import the .reg files :

[ Win + R ] regedit

And select "File > Import > C:\CIS-DISA-Windows-Server-2016\Reg\xxxx.reg"


3) Open the cmd console in the project folder, import the local group policy template, and apply it :

[ Win + R ] cmd

```
cd C:\CIS-DISA-Windows-Server-2016\
```
```
LGPO.exe /g .\GpoTemplate\
```
```
gpupdate /force
```

<<<<<<< HEAD
4) Open the powershell console with administrator privileges, then run the script "V-70639.ps1", and restart your server :
=======
Fourth step, check the NTFS permissions on the "eventvwr.exe" application in the %SystemRoot%\SYSTEM32 path.
>>>>>>> 7106a0a16a985339c36d45dfa60e1c823c9fdb26

```
cd .\Powershell
```
```
.\V-70639.ps1
```

5) check the NTFS permissions on the "eventvwr.exe" application in the %SystemRoot%\SYSTEM32 path.



## Finally

I am aware that this project is not perfect, so don't hesitate to suggest improvements!
