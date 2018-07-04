# BeatSaberSongLoader - Playlist fork
A fork of xyonico's plugin for adding custom songs into Beat Saber. This version allows for user-defined playlists using BeatDrop's format, including the performance improvements from Taz's version of the song loader.

*This mod works on both the Steam and Oculus Store versions.*

## Installation Instructions
 1. Download the latest release from here: https://github.com/jmontineri/BeatSaberSongLoader/releases
 2. Extract the .zip file into the `Oculus Apps\Software\hyperbolic-magnetism-beat-saber` for Oculus Home OR `steamapps\common\Beat Saber` for Steam. (The one with Beat Saber.exe)
  
    The Beat Saber folder should look something like this:
    * `Beat Saber_Data`
    * `CustomSongs`
    * `IPA`
    * `Plugins`
    * `Beat Saber (Patch & Launch)`
    * `Beat Saber.exe`
    * `IPA.exe`
    * `Mono.Cecil.dll`
    * `UnityPlayer.dll`
 3. Done!

## Usage
 1. Launch Beat Saber through the platform you purchased it on.	
 2. Use BeatDrop to generate a playlist
 3. Go to 'Solo' -> 'Standard' and the content of the playlist will be listed and ready to play below the official songs.


## Installing Custom Songs
The process is the same as xyonico's version/

The following files must be placed within their own folder inside the "CustomSongs" folder.

    Required files:
		1. cover.jpg (Size 256x256)
			-This is the picture shown next to song in the selection screen.
			-The name can be whatever you want, make sure its the same as the one found in info.json
			-Only supported image types are jpg and png
		2. song.wav / song.ogg
			-This is your song you would like to load
			-Name must be the same as in info.json
			-Only supported audio types are wav and ogg
		3. easy.json / normal.json / hard.json / expert.json
			-This is the note chart for each difficulty
			-Names must match the "jsonPath" in info.json
			-Use a Beat Saber editor to make your own note chart for the song
		4. info.json
			-Contains the info for the song

The following is a template for you to use:
```json
{
  "songName":"YourSongName",
  "songSubName":"ft. Name",
  "authorName":"AuthorName",
  "beatsPerMinute":179.0, 
  "previewStartTime":12.0,
  "previewDuration":10.0,
  "coverImagePath":"cover.jpg",
  "environmentName":"DefaultEnvironment",
  "difficultyLevels": [
	{ "difficulty":"Expert", "difficultyRank":4, "audioPath":"YourSong.wav", "jsonPath":"expert.json" },
	{ "difficulty":"Easy", "difficultyRank":0, "audioPath":"YourSong.ogg", "jsonPath":"easy.json" }
  ]
}
```
___

### info.json Explanation
```
"songName" - Name of your song
"songSubName" - Text rendered in smaller letters next to song name. (ft. Artist)
"beatsPerMinute" - BPM of the song you are using
"previewStartTime" - How many seconds into the song the preview should start
"previewDuration" - Time in seconds the song will be previewed in selection screen
"coverImagePath" - Cover image name
"environmentName" - Game environment to be used

All possible environmentNames:
-DefaultEnvironment
-BigMirrorEnvironment
-TriangleEnvironment
-NiceEnvironment

"difficultyLevels": [
	{
		"difficulty": This can only be set to Easy, Normal, Hard, Expert or ExpertPlus,
		"difficultyRank": Currently unused whole number for ranking difficulty,
		"audioPath": The name of your audio file,
		"jsonPath": The name of the json file for this specific difficulty
	}
  ]
```

# Keyboard Shortcuts
*(Make sure Beat Saber's window is in focus when using these shortcuts)*
---
 * Press <kbd>R</kbd> when in main menu to update song list and refresh the active playlist.

#License information

License information can be found in LICENSE.md. Original author is www.github.com/xyonico.
