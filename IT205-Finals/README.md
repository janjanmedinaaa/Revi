# IT205 Finals

<!-- ## Managing User Desktops with Group Policy

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
- used before the adapter’s DNS settings -->

## Installing, Configuring, and Troubleshooting the Network Policy Server Role

### Network Policy Server
- **RADIUS server**
    - performs centralized connection **authentication**, **authorization**, and **accounting for wireless**, **authenticating switch**, and **dial-up** and **VPN connections**
- **RADIUS proxy**
    - configure connection request policies that indicate which connection requests that the NPS server will forward to other RADIUS servers and to which RADIUS servers you want to forward connection requests
- **NAP policy server**
    - evaluates statements of health (SoHs) sent by NAP-capable client computers that attempt to connect to the network

### RADIUS Server
- **Remote Authentication Dial-In User Service**
- **client/server protocol and software that enables remote access servers** to communicate with a central server to authenticate dial-in users and authorize their access to the requested system or service

### RADIUS Client
- **send connection requests and accounting messages to RADIUS servers** for authentication, authorization, and accounting

### RADIUS Proxy
- receives connection attempts from RADIUS clients, and then forwards them to the appropriate RADIUS server or another RADIUS proxy for further routing
- **Required for:**
    - Offering outsourced dial-up, VPN, or wireless network-access services by service providers 
    - Providing authentication and authorization for user accounts that are not Active Directory members
    - Performing authentication and authorization by using a database that is not a Windows account database 
    - Load-balancing connection requests among multiple RADIUS servers 
    - Providing RADIUS for outsourced service providers and limiting traffic types through the firewall 

### Connection Request Policy
- sets of conditions and settings that designate which RADIUS servers perform the authentication and authorization of connection requests that NPS receives from RADIUS clients

### NPS monitoring methods
- **sEvent logging**
    - process of logging NPS events in the System Event log
    - useful for auditing and troubleshooting connection attempts
- **Logging user authentication and accounting requests** 
    - useful for connection analysis and billing purposes

## Implementing Network Access Protection

### Network Access Protection
- **Enforce health-requirement policies** on client computers
- **Ensure client computers** are compliant with policies
- Offer remediation support for computers that do not meet health requirements
- **NAP cannot:**
    - **Prevent authorized users with compliant computers from performing malicious activity on the network**
    - **Restrict network access for computers** that are running Windows versions previous to Windows XP SP2, when exception rules are configured for those computers

### IPsec Enforcement
- comprises a health certificate server and an IPsec NAP EC
- IPsec enforcement confines the communication on a network to those nodes that are considered compliant 
- You can define requirements for secure communications with compliant clients on a per-IP address or a per-TCP/UDP port-number basis

### VPN Enforcement
- Computer must be compliant to obtain **unlimited network access through a remote access VPN connection** 
- Noncompliant computers have **network access limited through a set of IP packet filters** that the VPN server applies to the VPN connection
- actively monitors the health status of the NAP client and then **applies the IP packet filters for the restricted network to the VPN connection** if the client becomes noncompliant 

### DHCP Enforcement
- Computers must be compliant to obtain an **unlimited access IPv4 address configuration from a DHCP server**
- Noncompliant computers have IPv4 address configuration, **allowing access to restricted network only**
- actively monitors the health status of the NAP client, **renewing the IPv4 address configuration for access only to the restricted network** if the client becomes noncompliant

### System Health Validators
- server software counterparts to system health agents

### Health Policy
- consist of one or more SHVs and other settings, which you can **use to define configuration requirements for NAP-capable computers** that attempt to connect to your network

### Remediation Server Groups
- list of servers on the restricted network that noncompliant NAP clients can access for software updates 
- **Remediation Server** 
    - hosts the updates that the NAP agent can use to bring noncompliant client computers into compliance with the health policy that NPS defines 

### NAP Tracing
- identifies NAP events and records them to a log file
- disabled by default, no NAP Events are recorded
- **Tracing Levels**
    - Basic
    - Advanced
    - Debug
- **Usage**
    - Evaluate the health and security of your network
    - For troubleshooting and maintenance

### Troubleshooting NAP
- `netsh NAP client show state`
- `netsh NAP client show config`
- `netsh NAP client show group`

## Optimizing File Services

### Capacity management challenges
- Determining **existing storage use**
- **Establishing and enforcing storage use with policies**
- Anticipating future requirements

### Addressing CMCs
- Analyzing **how storage is used**
- Defining storage resource management policies
- **Implementing policies** to manage storage growth
- **Implementing a system** for reporting and monitoring

### File Server Resource Manager (FSRM)
- role service in Windows Server that enables to managed and classified data stored on file server
- **Functionalities (SFSFC)**
    - Storage quota management
    - File screening management
    - Storage reports management
    - File management tasks
    - Classification management

### Quota Management
- limit disk space usage and provides notifications when thresholds are reached
- Quota Notifications
    - Send **email** notifications
    - **Log an event** in Event Viewer
    - **Run a command** or script
    - Generate storage **reports**

### Quota Templates
- **Defines:**
    - A space limit
    - The type of quota (hard or soft)
    - A set of notifications to be generated when the quota limit is approached

### Monitoring Quota Usage
- Viewing quota information in the **FSRM console**
- Generating a **quota usage report**
- **Creating soft quotas**
- Using the `Get-FSRMQuota` Windows PowerShell cmdlet

### File Screening Management
- provides a method for controlling the types of files that can be saved on file servers

### File Groups
- used to define a namespace for a file screen, file screen exception, or storage report
- **Pattern Groups**
    - Files to include
    - Files to exclude

### File screen templates
- Provide a definition for newly created file screens
- Enable control over file screens created from templates

### File screen exceptions
- Enable you to override file screens for a specific location or file group

### Storage Reports
- provide information about file usage on a file server

### Report Task Specifications
- The volumes and folders to report on
- Which reports to generate
- Which parameters to use
- How often to generate the reports
- Which file formats to save the reports in

### Classification Management
- enables you to **create and assign classification properties to files** using an automated mechanism

### Classification Properties
- **configurable value** that can be assigned to a file

### Classification Rule
- **applies Classification Properties** to file based on information about the file

### File Management Tasks
- enable administrators to perform operations on files based on assigned Classification Properties
- **Functionalities**
    - Move files to other locations
    - Archive expired files
    - Delete unwanted files
    - Rename files

### Distributed File System
- incorporates technologies that provide fault-tolerant access to geographically dispersed files
- **DFS Technologies**
    - DFS-N (*Namespace*)
    - DFS-R (*Replication*)

### DFS Namespace
- **Domain-based namespace**
    - Namespace is stored in AD DS
    - Increased redundancy for namespace hosting 
- **Standalone namespace**
    - Namespace is stored on the local server
    - Only redundant of stored on a failover cluster

### DFS Replication
- Uses Remote Differential Compression (RDC)
- Uses a staging folder to stage a file before sending or receiving it
- Detects changes on the volume by monitoring the USN journal
- Uses a vector version exchange protocol
- Recovers from failure 

### Data Deduplication
- optimizes volume storage by redirecting redundant data to single storage point

### Replication Group
- A set of servers that participate in replicating one or more replicated folders

### Replicated Folder
- A folder that is kept replicated on each server

### Troubleshooting DFS
- **Health Report**
    - Report replication statistics and general health of the topology
- **Propagation Test**
    - Generate a test file to verify replication
- **Propagation Report**
    - Report on the propagation test and provide replication statistics
- **Verify Topology**
    - Report on the current status of the members of the topology
- **Dfsrdiag.exe**
    - Monitor replication state of the DFS replication service

## Configuring Encryption and Advanced Auditing

### Encrypting File System (EFS)
- feature that can **encrypt files** that are stored on an **NTFS–formatted partition**
- acts as an *additional* layer of security
- can be used with **no pre-configuration**

### EFS Mechanics
- **Symmetric encryption** is used to protect the data
- **Public key encryption** is used to protect the symmetric key

### Recovering EFS–Encrypted Files
- Back up user certificates
- Configure a recovery agent

### Audit Policies
- By default, domain controllers audit success events for most categories
- **Over-auditing**
    - Logs are too big to find important events
- **Under-auditing**
    - Important events are not logged

### Enabling Audit Policy
- **Enable the appropriate settings** in the GPO
- **Apply the GPO to the AD DS** location where your servers are located

## Implementing Update Management

### Windows Server Update Service (WSUS)
- Software Update Services
- program developed by Microsoft that enables administrators to manage the distribution of updates and hotfixes released for Microsoft Products to computers in a corporate environment
- Phases
    - Assess
    - Identify
    - Evaluate and Plan
    - Deploy

### Computer Groups
- used to control how updates are applied
- used to organize WSUS clients

### Approving Updates
- Can be approved automatically but not recommended
- Updates should be tested first
- can be declined and removed

## Monitoring Windows Server 2012

### Task Manager
- helps you to identify and resolve performance-related issues

### Performance Monitor
- enables you to view current performance statistics, or to view historical gathered through the use of data collector sets

### Resource Monitor
- provides an in-depth look at the real-time performance of your server

### Event Viewer
- provides categorized lists of essential Windows log events, and log groupings for individual installed applications and specific Windows component categories

### Baseline, Trends, and Capacity Planning 
- you can more accurately interpret real-time monitoring information

### Establishing a Baseling
- Interpret Performance trends
- Perform capacity planning
- Identify bottlenecks

### Data Collector Sets
- enables you to gather performance-related and other system statistics for analysis
- Contains:
    - Performance Counters
    - Event Trace data
    - System configuration information

### Custom View
- allow you to query and sort just the events that you want to analyze

### Event Subscriptions
- allow you to collect event logs from multiple servers, and store them locally