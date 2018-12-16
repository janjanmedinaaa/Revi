# ICS 115 Finals (Cover to Cover)

## Basic Concepts and Tools

### Ways in Creating Mobile Applications
- **WebViews**
    - Used by **First cross-platform** frameworks
    - PhoneGap, Apache Cordova, Ionic
- **Reactive Views**
    - **Simplify the creation of WebViews** through the use of programming patterns borrowed from Reactive Programming.
    - React Native 
- **Flutter**
    - Takes a different approach to avoiding performance problems caused by the need for a JavaScript bridge by using Dart.
- **Native Applications**
    - Developed to be used on a **particular platform** or operating system
    - Built using the specific IDE for the given Operating Systems
    - Android, IOS

### Native Application - PROS AND CONS
- **PROS**
    - Fast and Responsive
    - Best Performance
    - **More Interactive**, Intuitive and run much smoother in terms of user Input and Output.
- **CONS**
    - **More expensive** to develop
    - **Require more time** to develop
    - **Higher cost** of maintenance

### Hybrid Applications
- Applications developed to be used across multiple platforms
- **Targets a WebView** hosted inside a native container.

### Hybrid Application - PROS AND CONS
- **PROS**
    - **Adaptable** to multiple platforms
    - Unified and **less expensive** development
    - **Faster development** time
- **CONS**
    - **Slower** app performance
    - Apps with heavy animations and sound effects aren’t as seamless as their native counterparts.

### Progressive Web Apps
- Web app that uses modern web capabilities to deliver an app-like experience to users
- Can always be **pinned or saved** on your phone’s home screen.

### Progressive Web Apps - PROS AND CONS
- **PROS**
    - **Easy** to build
    - Works **offline** and performs well on low-quality networks
    - One app for all platforms
- **CONS**
    - **Needs a browser** to run
    - Web apps are **less interactive and intuitive** than native apps

## Android Architecture
- **Linux Kernel**
    - **foundation** of the Android Platform
    - where the **Android Runtime relies**
- **Hardware Abstraction Layer (HAL)**
    - provides standard interfaces that expose device hardware capabilities to the higher-level Java API framework
- **Android Runtime (ART)**
    - written to run multiple virtual machines on low-memory devices by executing DEX files
    - **DEX Files**
        - bytecode format designed specially for Android that’s optimized for minimal memory footprint
- **Native C/C++ Libraries**
    - Many core Android system components and services, such as ART and HAL, are built from native code that require native libraries written in C and C++.
- **Java API Framework**
    - entire feature-set of the Android OS is available to you through APIs written in Java
- **System Apps**

## Persistent Storage in Android Application

### Methods of Saving Data
1. **Shared Preferences**
    - Store private primative data in key-value pairs
2. **Internal Storage**
    - Store private data on the device internal memory
3. **External Storage**
    - Store private data on the device external memory
4. **SQLite Database**
    - Store structured data in a private database.
5. **Network Connection**
    - Store data on the web with your own Network Server

### Private Files
- Files that rightfully belong to your app and should be deleted when the user uninstalls your app
- Doesn’t provide value to the user outside your app
`getExternalFilesDir()`
- Method to store private files on external storage

### Public Files
- Files that should be freely available to other apps and to the end user
- Not deleted when the user uninstalls the app
`getExternalStoragePublicDirectory()`
- Method to store public files on the external storage

### Shared Preferences 
- Allows you to save and retrieve persistent key-value pairs
- Generally used to store small amount of data, that may be required frequently.
- **Supported Data Types**: 
    - boolean
    - float
    - int
    - long
    - string
- **Editor Class Methods**: 
    - `apply()`
    - `clear()`
    - `remove(String key)`
    - `putLong(String key, long value)`
    - `putInt(String key, int value)`
    - `putFloat(String key, float value)`

#### Different Modes
- **MODE_APPEND** - append new preferences to existing
- **MODE_ENABLE_WRITE_AHEAD_LOGGING** - would enable write ahead logging by default
- **MODE_MULTI_PROCESS** - check for modification of preferences
- **MODE_PRIVATE** - file can only be accessed using calling application
- **MODE_WORLD_READABLE** - allow other application to read preferences
- **MODE_WORLD_WRITABLE** - allow other application to write preferences

### Internal Storage
- Allows reading and writing to files in the device internal memory


### Internal vs. External Storage
- **External**
    - Not always available
    - World-readable
    - System removes all app files upon uninstallation only when you use `getExternalFilesDir()`
    - Large Memory
- **Internal**
    - Always available
    - Only accessible by your app
    - System removes all app files upon uninstallation
    - Less memory
    - Access speed is more or less the same

### Shared Preferences vs Internal/External Storage
- **Shared Preferences**
    - Storing data in XML files
    - More efficient 
    - Only primative data types
- **Internal/External Storage**
    - Less efficient
    - Storing data to phone memory

### Cache Storage
- Files stored in the files folder are persistent and remain until they are deleted
- Files can be stored temporarily(caching)


## SQLite Database

### SQLite
- Scaled-down version of MySQL, PostgreSQL, and other RDBMS
- Each Application has its own SQLite DB
- Stored in `/data/data/<package-name>/databases`

### SQLiteOpenHelper
- Used to manipulate the SQLite Database


## Firebase Database

### JSON
- **Javascript Object Notation**
- More restricted compared to XML
- Format by **Douglas Crockford**
- Designed for human-readable data interchange
- `.json` file
- **Characteristics**
    - Easy to read and write
    - Lightweight 
    - Language Independent

### XML vs. JSON
- **XML (1997)**
    - Uses similar tags to HTML
- **JSON (2001)**
    - Can be condensed to reduce file size

### Firebase
- Fully managed platform for building **IOS, Android, and Web Apps** that provides automatic **data synchronization, authentication, messaging, file storage, analytics, and more**.