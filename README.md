# CasioEmu Example Plugin

An Android plugins for the [**CasioEmuMsvc**](https://github.com/telecomadm1145/CasioEmuMsvc).

## How to Build

### Prerequisites
- **Android Studio** (or Command Line Tools)
- **Android NDK** & **CMake** installed via SDK Manager.
- **Java 21**

### Build from Command Line
To build the release APK containing your compiled C++ plugin:
```bash
# On Linux/macOS
./gradlew assembleRelease

# On Windows
gradlew.bat assembleRelease
```
The output APK will be generated at: `app/build/outputs/apk/release/app-release.apk`

## 📄 License
This plugin is licensed under the **MIT License**. 
> [!IMPORTANT]
*Please note that the main `CasioEmuMsvc` application is licensed under the **GPLv3**. Depending on how your final plugin interacts with the emulator, distributing your compiled binaries may be subject to GPLv3 terms.*