# Simple Permissions

**IMPORTANT: This is a copy of the Simple Permissions plugin from Ethras ([https://pub.dartlang.org/packages/simple_permissions](https://pub.dartlang.org/packages/simple_permissions)). The plugin repository has since been deleted, so commit history cannot be retained. This repo is for temporary private use only (quick fix of an iOS issue before migrating to another permission plugin). I am not going to maintain this project, so please avoid using it.**

A new flutter plugin for checking and requesting permissions on iOs and Android.

## Getting Started

Make sure you add the needed permissions to your Android Manifest  [Permission](https://developer.android.com/reference/android/Manifest.permission.html)
and Info.plist.

```xml
<uses-permission android:name="android.permission.RECORD_AUDIO" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
```

## API
### List of currently available permissions

```dart
enum Permission {
  // Microphone
  RecordAudio,

  // Camera
  Camera,

  // Read External Storage (Android)
  ReadExternalStorage

  // Write External Storage (Android)
  WriteExternalStorage,

  // Access Coarse Location (Android) / When In Use iOS
  AccessCoarseLocation,

  // Access Fine Location (Android) / When In Use iOS
  AccessFineLocation,

  // Access Fine Location (Android) / When In Use iOS
  WhenInUseLocation,

  // Access Fine Location (Android) / Always Location iOS
  AlwaysLocation

  // Write contacts (Android) / Contacts iOS
  WriteContacts

  // Read contacts (Android) / Contacts iOS
  ReadContacts
}
```

```dart
/// Permissions status enum (iOS)
enum PermissionStatus { notDetermined, restricted, denied, authorized }
```

### Methods
```dart
  /// Check a [permission] and return a [Future] with the result
  static Future<bool> checkPermission(Permission permission);

  /// Request a [permission] and return a [Future] with the result
  static Future<PermissionStatus> requestPermission(Permission permission);

  /// Open app settings on Android and iOS
  static Future<bool> openSettings();
  
  /// Get iOs permission status 
  static Future<PermissionStatus> getPermissionStatus(Permission permission)
```
