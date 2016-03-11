# Xcode hidden features

*   [Show build operation duration on toolbar](#1)
*   [Disable swip gestures Xcode only](#2)

***

<h3 id="1">Show build operation duration on toolbar</h3>
```bash
defaults write com.apple.dt.Xcode ShowBuildOperationDuration YES
```

<h3 id="2">Disable swip gestures Xcode only</h3>
for magic mouse
```bash
defaults write com.apple.dt.Xcode AppleEnableMouseSwipeNavigateWithScrolls -bool NO
```
for trackpad
```bash
defaults write com.apple.dt.Xcode AppleEnableSwipeNavigateWithScrolls -bool NO
```
