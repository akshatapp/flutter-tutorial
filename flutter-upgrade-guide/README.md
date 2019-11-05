# flutter upgrade guide

## how to check flutter version ?
Run command :
```
$ flutter --version

//Output
Flutter 1.7.8+hotfix.4 • channel stable • https://github.com/flutter/flutter.git
Framework • revision 20e59316b8 (5 weeks ago) • 2019-07-18 20:04:33 -0700
Engine • revision fee001c93f
Tools • Dart 2.4.0
```

## how to select a specific flutter version ?
Run command :
```
$ flutter version v1.9.1+hotfix.3
```

## how to upgrade flutter sdk and packages ?
Run command :
```
$ flutter upgrade

//Output 
Upgrading Flutter from /home/dev/Desktop/workspace/flutter...
Updating d51fd86cd..20e59316b
 19 files changed, 61 insertions(+), 33 deletions(-)

Upgrading engine...
Downloading android-arm-profile/linux-x64 tools...                  1.0s
Downloading android-arm-release/linux-x64 tools...                  0.6s
Downloading android-arm64-profile/linux-x64 tools...                0.9s
Downloading android-arm64-release/linux-x64 tools...                1.4s
Downloading android-x86 tools...                                    2.4s
Downloading android-x64 tools...                                    2.1s
Downloading android-arm tools...                                    0.9s
Downloading android-arm-profile tools...                            0.8s
Downloading android-arm-release tools...                            0.5s
Downloading android-arm64 tools...                                  1.0s
Downloading android-arm64-profile tools...                          0.6s
Downloading android-arm64-release tools...                          0.5s
Downloading package sky_engine...                                   0.2s
Downloading common tools...                                         1.1s
Downloading common tools...                                         1.1s
Downloading linux-x64 tools...                                      3.3s

Flutter 1.7.8+hotfix.4 • channel stable • https://github.com/flutter/flutter.git
Framework • revision 20e59316b8 (5 weeks ago) • 2019-07-18 20:04:33 -0700
Engine • revision fee001c93f
Tools • Dart 2.4.0
```

## what are flutter channels ?
Flutter has following channels :

* stable channel 
  * Most Stable Build
  * Recommended channel for all production app releases

* beta channel
  * "best" dev build of the previous month

* dev channel 
  * latest fully-tested build
  
* master channel
  * Least Stable Build
  * latest cutting edge build

## how to view your current channel ?
Run command :
```
$ flutter channel

//Output 
Flutter channels:
* stable
  beta
  dev
  master
```
symbol * next to the channel name indicates your current channel

## how to switch between flutter channels ?
Run command  - use "flutter channel [channel-name]"
```
flutter channel dev
```
Using this command we can switch to dev channel

## what is flutter doctor ?
this is command that check your environment and displays report of the status of flutter installation.

```
$ flutter doctor

  Doctor summary (to see all details, run flutter doctor -v):
    [✓] Flutter (Channel stable, v1.9.1+hotfix.4, on Linux, locale en_US.UTF-8)
 
    [✓] Android toolchain - develop for Android devices (Android SDK version 29.0.2)
    [✓] Android Studio (version 3.5)
    [!] Connected device
    ! No devices available

    ! Doctor found issues in 1 category.
```

## what are some common errors while upgrading flutter ?
Error  : Missing "curl" tool. Unable to download Dart SDK.
```
sudo apt-get install curl 
```
Note : above command downloads and installs the curl tool required to download dart sdk

## Useful Resources

* [Flutter SDK Releases](https://flutter.dev/docs/development/tools/sdk/releases)
* [Flutter Upgrading](https://flutter.dev/docs/development/tools/sdk/upgrading)
* [Flutter Wiki](https://github.com/flutter/flutter/wiki/Flutter-build-release-channels)
