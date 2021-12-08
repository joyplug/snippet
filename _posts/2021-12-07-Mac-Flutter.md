---
layout: post
title:  "[Mac] VSCode & C/C++"
date:   2021-12-07 23:10:00 +0900
categories: [mac]
---

#### VScode
```bash
brew install cask
brew install --cask visual-studio-code
```
```bash
sudo xattr -dr com.apple.quarantine /Applications/Visual\ Studio\ Code.app
```
```bash
code --install-extension dart-code.flutter
```
<br>

#### Xcode
```bash
sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
sudo xcodebuild -runFirstLaunch
sudo xcodebuild -license
sudo gem install cocoapods
```
<br>

#### Android Studio
`Android Studio` -> `Preferences` -> `Appearance & Behavior` -> `System Settings` -> `Android SDK` -> `SDK Tools` -> `Android SDK Command-line Tools`

> AVD Manager  
```bash
brew install --cask android-platform-tools
```
<br>

#### Flutter SDK
```bash
cd ~/Documents/Project/flutter
git clone https://github.com/flutter/flutter.git -b stable 
code ~/.zshrc 
export PATH=$PATH:$HOME/Documents/Project/flutter/flutter/bin 
flutter doctor --android-licenses 
flutter create my_app 
cd my_app flutter run
```

> 안드로이드 에뮬레이터에서 실행오류 발생 시 해당 SDK Version 설치하기 
`project/app/build.gradle` -> `compileSdkVersion 31`

#### Dart
[https://dartpad.dartlang.org](https://dartpad.dartlang.org)
