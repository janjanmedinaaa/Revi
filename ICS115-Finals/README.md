# ICS 115 Finals

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