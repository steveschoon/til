# Mouse Acceleration

My Razor mice that I use feel way to twitchy with default settings after macOS reboots.  This feels smoother:

```
defaults write .GlobalPreferences com.apple.mouse.scaling -1
```

To check the current setting:

```
defaults read .GlobalPreferences com.apple.mouse.scaling
```
