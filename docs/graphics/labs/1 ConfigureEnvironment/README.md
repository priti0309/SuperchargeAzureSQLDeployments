## Lab 1 - Configure your Local Environment
--------------------------------

| Lab Description | This lab covers the installation of tools that you will you in the labs. |
| :------------ | :-------------- |
| Estimated Time to Complete | 20 minutes |
| Key Takeaways | 1. Download and install the required tools |
|  | 2. Know what version of the tools are installed |
|  | By the end of this lab, you should have: Git, Visual Studio - SSDT, Visual Studio Code, Azure PowerShell, SSMS, Azure Data Studio, SQLPackage.exe |
| Author | Frank Garofalo |

### Purpose

For those new to DevOps, Source Control, and Database Projects
there are many tools that you need to familiarize yourself with. This modules
walks you through installing and configuring the required tools for this lab, as well as making sure they are on the current supported versions.

## Exercise - Setup Az PowerShell Module

### Launch PowerShell

1.  Right Click on **Windows PowerShell** from either the Desktop or the
    Start Menu

2.  Select **Run as Administrator**

### Set PowerShell Execution Policy

1.  Run the following PowerShell Command to set your execution policy to
    Unrestricted:

```powershell
Set-ExecutionPolicy Unrestricted
```

2.  Select Yes if prompted. Execution policies determine whether you can
    load configuration files, such as your PowerShell profile, or run
    scripts and whether scripts must be digitally signed before they are
    run. More information on this topic can be found here:
    <https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6#parameters>

### Install Az Module

1.  Run the following PowerShell Command:

```powershell
Install-Module -Name 'Az'
```

2.  If not already installed, you may be prompted to install the NuGet
    provider. Select **Yes** if this is the case.

3.  You may receive a warning message stating you are installing modules
    from an untrusted repository. Select **Yes** if this is the case.
    This process may take several minutes.

4.  Run the following PowerShell Command to verify the module has
    installed correctly:

```powershell
Get-Module -Name '*Az*' -ListAvailable
```

5.  If installed, Az should be returned

6.  Run the following PowerShell Command to turn off autosaving Azure
    credentials\
    (some Azure PowerShell versions have this on as the default)

```powershell
Disable-AzContextAutosave
```

<div style="page-break-after: always;"></div>

Expected return:

> PS C:\\\> Disable-AzContextAutosave
>
> Mode : Process
>
> ContextDirectory :
>
> ContextFile :
>
> CacheDirectory :
>
> CacheFile :
>
> Settings : {}

<div style="page-break-after: always;"></div>

## Exercise - Setup Git for Windows

### Download Git for Windows Installation Files

1.  In a web browser, navigate to <https://git-scm.com/download/win>

2.  The 64-bit version of **Git for Windows** should begin automatically
    downloading, if it does not select **64-bit Git for Windows Setup**

3.  Note the location of the installation files

### Install Git for Windows

1.  Run the **Git for Windows** installation file

2.  Accept the EULA by clicking **Next**

3.  Accept the default Destination Location and click **Next**

4.  Accept the default Components and click **Next**

5.  Accept the default Start Menu Folder of "Git" and click **Next**

6.  Accept the default editor of Vim and click **Next**

7.  Accept the default "Git from the command line and also from
    3rd-party software" and click **Next**

8.  Accept **OpenSSL** as the default HTTPS transport backend and click
    **Next**

9.  Accept the default **Windows-style** "Configuring the line ending
    conversions" and click **Next**

10. Accept the default **MinTTY** terminal emulator and click **Next**

11. Accept the default Configuring extra options and click **Next**

12. Click **Install**

13. Uncheck "View Release Notes" and click **Finish**

<div style="page-break-after: always;"></div>

## Exercise - Setup Visual Studio Code

### Download Visual Studio Code

1.  In a web browser, navigate to <https://code.visualstudio.com>

2.  Click **Download for Windows**

3.  Note the location of the installation files

### Install Visual Studio Code

1.  Run the **VSCodeUserSetup** installation file

2.  If you are prompted with a message \"This User Installer is not
    meant to be run as an Administrator\" Click **OK**

3.  Accept the EULA and click **Next**

4.  Accept the default installation location and click **Next**

5.  Accept the default Start Menu Folder and click **Next**

6.  Select all additional tasks and click **Next** (Optional)

7.  Click **Install**

8.  Uncheck "Launch Visual Studio Code" and click **Finish**

<div style="page-break-after: always;"></div>

## Exercise - Setup Azure Storage Explorer

### Download Azure Storage Explorer

1.  In a web browser, navigate to
    <https://azure.microsoft.com/en-us/features/storage-explorer/>

2.  Click **Download Storage Explorer free**

3.  Note the location of the installation files

### Install Azure Storage Explorer

1.  Run the Azure Storage Explorer installation file

2.  Accept the EULA and click **Install**

3.  Accept the default location and click **Next**

4.  Accept the Start Menu Folder and click **Next**

5.  After the installation completes, uncheck "Launch Microsoft Azure
    Storage Explorer" and click **Finish**

<div style="page-break-after: always;"></div>

## Exercise - Version Check

### Check the version of Az

1.  Launch VS Code

2.  Select the terminal. This is typically in the lower right pane of VS
    Code and is often tabbed with other panes, such as Problems, Output,
    and Debug Console. If you do not see Terminal, click View in the top
    menu bar and click **Terminal**.

3.  Type the following PowerShell command:

```powershell
Get-Module -Name 'Az.Compute' -ListAvailable | Select-Object -Property 'Version'
```

4.  The expected output is **2.4.1** or later

### Check the version of Git for Window

1.  From within the VS Code Terminal, Type the following git command:

```powershell
git --version
```

2.  The expected output is **git version 2.23.0.windows.1** or later

3.  If you experience any issues with this step, restart VS Code and try
    again

### Check the version of Visual Studio Code

1.  From the VS Code File Menu, click **Help** then **About**

2.  The expected version is **1.37.1** or later

### Check the version of Azure Storage Explorer

1.  Launch Azure Storage Explorer

2.  From the File Menu, click **Help** then **About**

3.  The expected version is **1.9.0** or later

<div style="page-break-after: always;"></div>

## Troubleshooting

**Azure PowerShell**\
\
We have seen issues in previous workshops if a system has multiple
versions of the Azure PowerShell module installed. If you run into
module related issues, remove **all Azure modules** from\
C:\\Program Files\\WindowsPowerShell\\Modules and install the Azure
module again.

While it is technically possible to have both the Az and AzureRM
PowerShell modules installed, we recommend removing the AzureRM modules
and using only the Az modules.

The Az PowerShell module requires .Net Framework Runtime 4.7.2 or higher

**Azure subscriptions**

<ins>TRIAL SUBSCRIPTIONS ARE NOT SUPPORTED FOR THIS WORKSHOP</ins>

<div style="page-break-after: always;"></div>