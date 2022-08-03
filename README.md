<p align="center">
  <img width="200" height="200" src="https://github.com/rohan-bhautoo/Audio_Player/blob/main/logo.png">
</p>
<h1 align="center">Audio Player</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.0.0-brightgreen.svg" />
  <img alt="Flutter" src="https://img.shields.io/badge/Flutter-027DFD?logo=flutter&logoColor=white" />
  <img alt="Dart" src="https://img.shields.io/badge/Dart-027DFD?logo=dart&logoColor=white" />
</p>

## Description
> Audio recorder from microphone to a given file path.

## Prerequisite

### Flutter
> Flutter is an open source framework by Google for building beautiful, natively compiled, multi-platform applications from a single codebase. Download it [here](https://docs.flutter.dev/get-started/install).

### pubspec.yaml

#### path_provider 2.0.11
> A Flutter plugin for finding commonly used locations on the filesystem. Supports Android, iOS, Linux, macOS and Windows. Not all methods are supported on all platforms. Check the documentation [here](https://pub.dev/packages/path_provider).

#### audioplayers 1.0.1
> A Flutter plugin to play multiple simultaneously audio files, works for Android, iOS, Linux, macOS, Windows, and web. Check the documentation [here](https://pub.dev/packages/audioplayers).

#### record 4.3.2
> Audio recorder from microphone to a given file path. Check the documentation [here](https://pub.dev/packages/record).

### Permissions

#### Android

```xml
<uses-permission android:name="android.permission.RECORD_AUDIO" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
```

#### IOS

```xml
<key>NSMicrophoneUsageDescription</key>
<string>We need to access to the microphone to record audio file</string>
```

## Usage

```dart
// Import package
import 'package:record/record.dart';

final record = Record();

// Check and request permission
if (await record.hasPermission()) {
  // Start recording
  await record.start(
    path: 'aFullPath/myFile.m4a',
    encoder: AudioEncoder.aacLc, // by default
    bitRate: 128000, // by default
    sampleRate: 44100, // by default
  );
}

// Get the state of the recorder
bool isRecording = await record.isRecording();

// Stop recording
await record.stop();
```

## Author

👤 **Rohan Bhautoo**

* Github: [@rohan-bhautoo](https://github.com/rohan-bhautoo)
* LinkedIn: [@rohan-bhautoo](https://linkedin.com/in/rohan-bhautoo)

## Show your support

Give a ⭐️ if this project helped you!
