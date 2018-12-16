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

### Android Architecture
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

## Android Projects and API

### Android View
- `manifests` folder
    - Contains the `AndroidManifest.xml` file
- `java` folder
    - Contains the **Java source code** files
    - including **JUnit test** code.
- `res` folder
    - Contains all non-code resources, such as **XML layouts**, UI **strings**, and bitmap **images**

### Project View
- `build` folder
    - Contains **build outputs**
- `libs` folder
    - Contains **private libraries**
- `src` folder
    - Contains all **code and resource** files
    - `androidTest` folder
        - Contains code for **instrumentation tests** that run on an Android device
    - `main` folder
        - Contains the *main* source set files
- `build.gradle`
    - defines the **module-specific build configurations**

### Android App Components
- **Activities**
    - **entry point** for interacting with the user
    - represents a **single screen**
- **Services**
    - **runs in the background** to perform long-running operations or to perform work for remote processes
- **Broadcast Receivers**
    - enables the system to deliver events to the app outside of a regular user flow, allowing the app to **respond to system-wide broadcast announcements**
- **Content Providers**
    - **manages a shared set of app data** that you can store in the file system

## Android User Interface

### Wireframes
- structural blueprints of sorts for the content you are planning to present via your app

### UI Controls
- **TextView** - Display text
- **EditText** - Input text
- **AutoCompleteTextView** - shows a list of completion suggestions automatically
- **Button** - pressed or clicked to perform actions
- **ImageButton** - shows and Image as a button
- **Checkbox** - on/off switch
- **ToggleButton** - on/off button with a light indicator
- **RadioButton** - either checked or unchecked

### UI Layouts
- **LinearLayout** - aligns all children in a single direction, **vertically or horizontally**
- **RelativeLayout** - displays child views in **relative positions**
- **ConstraintLayout** - layout child views using *constraints*
- **TableLayout** - groups views into **rows and columns**
- **FrameLayout** - **placeholder on screen** that you can use to display a single view
- **ListView** - displays a list of **scrollable items**
- **GridView** - displays items in a two-dimensional or a **scrollable grid**

### Extensible Markup Language (XML)
- tagging language **much like HTML** used to describe data
- **used in Android development** for different purposes, including defining the screen layout
- **readable** by both human and machine
- **scalable and simple** to develop

### Some Android Project Files

#### AndroidManifest.xml
- define all the components of our application

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.medina.falcutila.farey">

    /* App User Permissions */
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-feature android:name="android.hardware.location.gps" />
    <uses-permission android:name="android.permission.INTERNET" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <meta-data
            android:name="com.google.android.geo.API_KEY"
            android:value="@string/google_maps_key" />

        <activity
            android:name=".MapsActivity"
            android:label="@string/title_activity_maps">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        <activity android:name=".PricesActivity"></activity> // How other Screens are added
    </application>

</manifest>
```

#### strings.xml
- define all the strings in this XML file and then access them in our app
```
<resources>
    <string name="app_name">Farey</string>
    <string name="title_activity_maps">Farey</string>
    <string name="display_title">COMMON TAXI FARE</string>
    <string name="main_taxi_cab">Taxi Cab</string>
    <string name="book_now">BOOK NOW</string>
</resources>
```

#### styles.xml
- define different styles and looks for the UI
```
<resources>
    <!– Base application theme.  –>
    <style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
        <!– Customize your theme here.  –>
    </style>
</resources>
```

#### colors.xml
- define the color codes that we used in our app
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <!– define your colors Here –>
    <color name="greenColor">#0f0</color>
    <color name="white">#fff</color>
</resources>
```

#### dimens.xml
- define the dimensions of the Views
```
<resources>
    <!– Default screen margins, per the Android Design guidelines.–>
    <dimen name="activity_horizontal_margin">16dp</dimen>
    <dimen name="activity_vertical_margin">16dp</dimen>
    <dimen name="btnheight">50dp</dimen>
</resources>
```

## Styles, Themes, and Material Design

### Styles
- defines the format and look for a UI
- can be applied to an individual View or entire Activity or application
- defined in an **XML**

### Themes
- Android style applied to an entire Activity or application
- To set a theme for all activities:
    - edit `<application android:theme=@style/CustomStyle />`
- To set a theme for one activity:
    - edit `<activity android:theme=@style/CustomStyle />`

### Material Design
- comprehensive guide for visual, motion, and interaction design across platforms and devices
- Main purpose is creation of new visual language that combines principles of good design with technical and scientific innovation

## Android Lifecycle

### Activity 
- represents a single screen
- must be declared in your `AndroidManifest.xml` file
- main activity must be declared in the manifest with an `<intent-filter>` that includes the **MAIN** action and **LAUNCHER** category

### Android Callback Methods
- `onCreate()`
    - first callback and called when the activity is first created
- `onStart()`
    - activity becomes visible to the user
- `onResume()`
    - user starts interacting with the application
- `onPause()`
    - current activity is being paused and the previous activity is being resumed
    - does not receive user input and cannot execute any code
- `onStop()`
    - activity is no longer visible
- `onDestroy()`
    - activity is destroyed by the system
- `onRestart()`
    - activity restarts after stopping it

### Advantages of Good Callback Implementations
- avoid **crashing** if the user receives a phone call or switches to another app while using your app
- avoid **consuming valuable system resources** when the user is not actively using it
- avoid **losing the user’s progress if they leave your app** and return to it at a later time
- avoid **crashing or losing the user’s progress when the screen rotates**

### Application
- every app has 1 main activity and other activities
- when a new activity starts, the previous activity is stopped and added to a stack known as *backstack*

### Logcat
- for debugging purposes
- **Methods**
    - `Log.i(String tag, String message)` - Information 
    - `Log.e(String tag, String message)` - Error 
    - `Log.w(String tag, String message)` - Warning 
    - `Log.v(String tag, String message)` - Verbose
    - `Log.d(String tag, String message)` - Debug

### Toast vs. Snackbar
- Toast
    - customised and printed anywhere on the screen
    - don’t have action button
    - cannot be off until the time limit finish
    - `Toast.makeText(getApplicationContext(), 'Message', Toast.LENGTH_SHORT).show()`
- Snackbar
    - only showed in the bottom of the screen
    - may have a maximum of 1 action button optionally
    - can be swiped off before the time limit
    - `Snackbar.make(coordinatorLayout, 'Message', Snackbar.LENGTH_LONG).show()`

## Explicit and Implicit Intent

### R Class
- generated when the Android Application is compiled
- contains resource IDs for all the resources available in your res/ directory

### Android App Components
- **Activities**
    - Represents a **Single Screen**
    - Extends `Activity` Base Class
- **Services**
    - **Runs in Background**
    - Extends `Service` Base Class
- **Intent/Broadcast Receiver**
    - **Receives and Reacts to Broadcast Intents**
    - No UI but **can start an Activity**
    - Extends `BroadcastReceiver` Base Class
- **Content Provider**
    - **Makes application data available to other apps**
    - Extends `ContentProvider` Base Class

### Services
- **runs in the background** to perform long-running operations **without needing to interact with the user**
- it works even if application is destroyed
- **States**
    - Started
        - when an application component, such as an activity, starts it by calling `startService()`
    - Bound
        - when an application component binds to it by calling `bindService()`

### IntentService
- can be used in long tasks usually with **no communication to main thread**
- triggered using an **Intent**
- it spawns a **separate worker thread** and the method `onHandleIntent()` is called on this thread

### Intent
- **message that is passed between components** such as Activities, Content Providers, Broadcast Receivers, Services, etc.

### Explicit vs. Implicit Intents
- **Explicit**
    - **specifies** the component
    - Starts Broadcast Receivers, Activities, Background Services
    - `Intent i = new Intent(Intent.ACTION_VIEW);`
- **Implicit**
    - **doesn't specify** the component
    - Starts Map Geolocation, Website in Webview, Dialer
    - `Intent i = new Intent(getApplicationContext(), ActivityTwo.class);`

### Pieces of Intent
- **Action** - defines what you want to do
- **Data** - what type of data do you want to work with
- **Extras** - what additional information you need to provide
- **Categories** - create groups of components to handle the intent

### Intent Filter
- Defined mostly in your manifest but may also be dynamically registered in code.
- Describe what **ACTION**, **DATA**, or **CATEGORIES** that a component can handle.
- Children of `<intent-filter>`
    - `<action>`
        - actions can be handled by your component
    - `<category>`
        - grouping does your component support
    - `<data>`
        - what data can be handled by your component

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

### Sample Firebase Code
```
/* Create Firebase Instance and Database References */
FirebaseDatabase db = FirebaseDatabase.getInstance();
DatabaseReference reference = db.getReference("RideShare");

/* To listen for Firebase Database Changes */
reference.addValueEventListener(new ValueEventListener() {
    @Override
    public void onDataChange(DataSnapshot dataSnapshot) {
        for(DataSnapshot ds : dataSnapshot.getChildren()) {
            
        }
    }

    @Override
    public void onCancelled(DatabaseError databaseError) {
        System.out.println("The read failed: " + databaseError.getCode());
    }
});
```