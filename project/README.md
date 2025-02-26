# Audio Extractor/Downloader
### Video Demo: https://youtu.be/QPJATpX06gQ
## What it does:
My project is an audio extractor and downloader that automatically downloads all songs on a Spotify playlist or album onto your computer for your convenience (offline music for free). The program will also download audio from YouTube playlists or videos. All files will be downloaded to a downloads folder in the running directory.

## Options:
### Spotify:
Using the Spotify option, you can automatically download all songs in any playlist or album on Spotify to your computer. This option uses the Spotify library and Spotify's API to get all track names and artists from a playlist or album. Then, using the Pytube library, we will search for names and artists on YouTube and download the first result.

### YouTube playlist:
The YouTube Playlist option is exactly what it seems. Will accept a YouTube playlist link or a link to a video in a playlist, and using Pytube's Playlist() function, download all audio from each video in the playlist.

### Single video:
The Single video option will download the audio of any YouTube not marked as private.

## Design choices:
### Authorization Code Flow:
I decided to use an authorization code flow instead of a client credentials flow because I didn't want the user to have to have their own Spotify account to use the program. The authorization code flow uses separate environment variables in a .env file to authorize access to the Spotify API.

### Tabulate:
I decided not to use a GUI or web-based program but still wanted my program to be easily accessible and usable. So I used Tabulate to print tables that are easily readable and easy to understand.

## Problems I ran into:
### GUI or No GUI:
I initially started the program with the intention of making a GUI for efficient use of the program. But since I was working in github codespaces, it is more complicated than just using your preferred gui library. So I decided to do a terminal-based program instead.

### Promblems with the pytube library:
Using other libraries always comes with the risk of having their own problems. That is exactly what happened with Pytube. There was a problem when using the Search() function, where an "unexpeded renderer occurred" message would show in the terminal every time when using the function. The program would still work perfectly every time, but there was no way to suppress the message without changing the library's files. So I did some research and found out that this specific problem was caused by YouTube shorts. YouTube shorts are a fairly new concept, so there was no official fix, so I turned to GitHub and found that Rgryta had made a fix to suppress these warnings.
