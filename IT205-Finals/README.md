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

## Configuring and Troubleshooting Remote Access

### Network Policy and Access Services Role
- Enforce health policies
- Help to secure wireless and wired access
- Centralize network policy management

### Remote Access Role
- Provide **remote users access to resources** on a private network over a VPN or dial-up connection
- Provide **NAT services**
- Provide **LAN and WAN routing services** to connect network segments
- Enable and configure DirectAccess

### Network Authentication vs. Authorization
- **Authentication**
    - Verifies the **credentials of a connection attempt**
    - Uses an authentication protocol to send the credentials from the remote access client to the remote access server in either plain text or encrypted form
- **Authorization**
    - Verifies that the **connection attempt is allowed**
    - Occurs after successful authentication

### Authentication Methods
- **PAP**
    - Uses plaintext passwords
    - The **least secure** authentication protocol
- **CHAP**
    - **challenge-response authentication protocol** that uses the industry-standard MD5
    - improvement over PAP in that the password is not sent over the PPP link
- **MS-CHAPv2**
    - Provides two-way authentication, also known as **mutual authentication**
    - Provides **stronger security than CHAP**
- **EAP**
    - Allows for **arbitrary authentication** of a remote access connection through the use of authentication schemes, known as EAP types
    - Offers the **strongest security** by providing the **most flexibility in authentication variations**

### VPN Reconnect
- **maintains connectivity across network outages**
- provides seamless and consistent VPN connectivity 
- **IKEv2 technology** 
- **Automatically re-establishes VPN connections** when connectivity is available
- Maintains the connection if users move between different networks
- **Provides transparent connection status** to users

### VPN Server Configuration Requirements
- Public and private **network interfaces**
- **IP Address allocation** (static pool or DHCP)
- **Authentication provider** (NPS/RADIUS or the VPN server)
- DHCP relay agent considerations 
- Membership in the Local Administrators group or equivalent 

### Connection Manager Administration Kit
- Allows you to **customize users’ remote connection experience** by creating predefined connections on remote servers and networks
- **Creates an executable file that can be run on a client computer** to establish a network connection that you have designed

### Network Policy
- **Elements**
    - Conditions
    - Constraints
    - Settings
- **Steps**
    - Determine authorization by user or group 
    - Determine appropriate settings for the user account’s network access permissions

### DirectAccess
- **Connects automatically to corporate network over the public network**
- Uses various protocols, including HTTPS, to establish IPv6 connectivity
- Allows remote users to connect directly to intranet servers 
- **Support**
    - selected server access and IPsec authentication
    - end-to-end authentication and encryption
    - management of remote client computers

### Name Resolution Policy Table
- table that defines DNS servers for different namespaces and corresponding security settings
- used before the adapter’s DNS settings
