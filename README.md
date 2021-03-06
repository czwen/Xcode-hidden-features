# Xcode hidden features

*   [Show build operation duration on toolbar](#1)
*   [Disable swip gestures Xcode only](#2)
*   [Reduce Xcode build times](#3)
*   [Validating Your Version of Xcode](#4)
*   [Check Xcode UUID](#5)
*   [Clean Up Xcode Simulator](#6)

******

<h3 id="1">Show build operation duration on toolbar</h3>

```
defaults write com.apple.dt.Xcode ShowBuildOperationDuration YES
```

<h3 id="2">Disable swip gestures Xcode only</h3>
for magic mouse

```
defaults write com.apple.dt.Xcode AppleEnableMouseSwipeNavigateWithScrolls -bool NO
```

for trackpad

```
defaults write com.apple.dt.Xcode AppleEnableSwipeNavigateWithScrolls -bool NO
```

<h3 id="3">Reduce Xcode build times</h3>

source [https://coderwall.com/p/1p4mha/reduce-xcode-build-times](https://coderwall.com/p/1p4mha/reduce-xcode-build-times)

*   Try remove `~/Library/Developer/Xcode/DerivedData/`

```
$ rm -rf ~/Library/Developer/Xcode/DerivedData/*
```

*   Creating a 2 GB volume RAM disk via the Terminal:

```
$ hdid -nomount ram://4194304
```

*   hdid outputs the device name of the RAM disk. Change the number instead of the 'N' for newfs_hfs and diskutil commands.

```
$ newfs_hfs -v DerivedData /dev/rdiskN
$ diskutil mount -mountPoint ~/Library/Developer/Xcode/DerivedData /dev/diskN
```

<h3 id="4">Validating Your Version of Xcode</h3>

source [Validating Your Version of Xcode](https://developer.apple.com/news/?id=09222015a)

```
$ spctl --assess --verbose /Applications/Xcode.app
```

and the result

```
/Applications/Xcode.app: accepted source=Apple System
```

<h3 id="5">Check Xcode UUID</h3>

```
defaults read /Applications/Xcode.app/Contents/Info DVTPlugInCompatibilityUUID
```


<h3 id="6">Clean Up Xcode Simulator</h3>

```
xcrun simctl erase all
```

```
xcrun simctl delete unavailable
```
