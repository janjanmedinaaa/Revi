# IT205 Finals

## Managing User Desktops with Group Policy

### Administrative Templates
- Provide you with the ability to **control both the environment of the operating system and user experience**
- **Sections for computers**
    - Control Panel
    - Network
    - Printers
    - System
    - Windows components 
- **Sections for users**
    - Control panel 
    - Desktop
    - Network
    - Start menu and taskbar
    - System
    - Windows components

### ADM Files
- copied into every GPO in SYSVOL
- difficult to customize

### ADMX Files
- Include language-neutral ADML files that provide the localized language
- not stored in the GPO
- extensible through XML

### Central Store
- central repository for ADMX and ADML files
- stored in SYSVOL
- Must be created manually
- Is detected automatically by Windows Vista or Windows Server 2008

### Folder Redirection
- feature that allows folders to be located on a network server, but appear as if they are located on the local drive 
- **Configuration options**
    - Basic folder redirection
        - all users save their files to the **same location**
    - Advanced folder redirection
        - server hosting the folder location is based on **group membership**
    - Follow the Documents folder
        - force certain folders to **become subfolders of Documents**
- **Target folder location options**
    - Redirect to the **users’ home directory** (*Documents folder only*) 
    - Create a folder for each user under the root path 
    - Redirect to the following **location** 
    - Redirect to the **local user profile location**

### Group Policy Settings for Applying Scripts
- Computers
    - Startup scripts
    - Shutdown scripts
- Users
    - Logon scripts
    - Logoff scripts

### Group Policy Preferences
- Enable IT professionals to configure, deploy, and manage  settings that were not manageable by using Group Policy
- Are natively supported on Windows Server 2008 and Vista SP2 or newer
- created, deleted, replaced, or updated    

### Windows Installer
- **Fully automates the software installation and configuration process**
- Modifies or repairs an existing application installation
- Benefits
    - **Custom** installations 
    - **Resilient** applications 
    - **Clean** removal