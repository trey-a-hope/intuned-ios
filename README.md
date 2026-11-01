# inTuned (iOS)

An early iOS prototype for inTuned, the social music app also built for [Android](https://github.com/trey-a-hope/intuned.android). This version is a 2015-2016 Swift experiment with the device music library: type a track number, and the app plays that song from your library and shows when you last played it.

## What it does

- `MediaController.swift` loads the songs from the device library with `MPMediaQuery`/`MPMediaItemCollection` and can play, pause and look up a song by index, including its last played date.
- `ViewController.swift` is the single screen: a text field for the track index and a button that plays the song and shows "Last Played Date" in an alert, with play/pause handled through notifications.
- `UserController.swift` keeps the current user's song info, `Song.swift` models a song (title, artist, genre, BPM, media item, last played date), and `AlertMessage.swift` shows errors for an empty field or a track number out of range.
- UI is in `Base.lproj/Main.storyboard`, with a launch screen XIB.

## Tech stack

- Swift 1.x era syntax (for example `String.toInt()` and `UIAlertView`), MediaPlayer framework
- Xcode project `inTuned.xcodeproj`, iOS deployment target 8.4

## Running it

Open `inTuned.xcodeproj` in Xcode and run on a device with songs in its music library (the simulator has no media library). Current Xcode won't compile Swift 1.x code as is, so the sources need migrating to modern Swift first.
