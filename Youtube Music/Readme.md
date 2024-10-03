# YouTube Music Player Script

This is a Bash script that allows you to search, play, download, and manage YouTube music directly from your terminal. The script provides a menu-driven interface using `rofi` and integrates with `mpv`, `yt-dlp`, and SQLite to provide a powerful and lightweight YouTube music player experience.

## Features

- **Search and Play YouTube Music**: Search for music on YouTube, select a song, and play it via `mpv`.
- **Manage Downloaded Music**: Download YouTube songs as audio files, play or delete downloaded songs.
- **Control Playback**: Play, pause, stop, skip next or previous tracks directly from the interface.
- **Manage Playlist**: Add songs to an SQLite-based playlist, play songs from the playlist, or delete them.
- **Notifications**: Get desktop notifications when a song starts playing or when downloads are completed.

## Prerequisites

1. **Rofi**: For the menu-driven interface.
2. **mpv**: A media player for playing music.
3. **yt-dlp**: For downloading music from YouTube.
4. **SQLite3**: For managing the playlist.
5. **notify-send**: For desktop notifications.

Install the required dependencies on your system using your package manager. For example, on Ubuntu/Debian:

```bash
rofi mpv yt-dlp sqlite3 libnotify-bin
```

## Script Overview

### Variables

- `current_url_file`: Stores the current URL of the song being played.
- `music_download_dir`: The directory where downloaded songs are saved.
- `search_cache`: Stores the results of previous YouTube searches to avoid redundant requests.
- `mpv_pid_file`: Tracks the process ID of the `mpv` player to control playback.
- `db_file`: SQLite database file for managing the playlist.

### Functions

- `init_db`: Initializes the SQLite playlist database.
- `rofi_menu`: Displays a menu using `rofi`.
- `search_youtube`: Searches YouTube for a song or video.
- `start_mpv_if_needed`: Starts `mpv` if it's not already running.
- `is_music_playing`: Checks if music is currently playing.
- `play_song`: Plays a song using `mpv`.
- `add_to_playlist`: Adds a song to the playlist.
- `get_playlist_names`: Retrieves all playlist song names.
- `get_song_url_by_name`: Fetches the URL of a song by its name from the playlist.
- `play_from_playlist`: Plays a song from the playlist.
- `control_playback`: Provides options to control music playback (play, pause, stop, next, previous).
- `download_youtube_song`: Downloads a song from YouTube as an audio file.
- `play_downloaded_music`: Plays downloaded music from the local directory.
- `delete_downloaded_music`: Deletes downloaded music from the local directory.
- `main_menu`: The main menu that provides options for different actions.

### Main Menu

When you run the script, you are presented with the following options:

1. **Search and Play**: Search for music on YouTube and play it.
2. **Manage Downloads Music**: Download, play, or delete downloaded music files.
3. **Control Playback**: Control the currently playing music (play, pause, stop, etc.).
4. **Manage Playlist**: Add, play, or delete songs from your playlist.
5. **Quit**: Exit the script.

### Example Usage

1. To run the script, save it as `file_name` and make it executable:
   ```bash
   chmod +x file_name
   ```
2. Execute the script:
   ```bash
   ./file_name
   ```

## Additional Information

- The script saves downloaded music in your `~/Music` directory by default.
- Search results from YouTube are cached in the `$HOME/Music/.youtube_music_search_cache` file for faster searches in the future.
- The playlist is stored in an SQLite database located at `$HOME/Music/.playlist.db`.

Enjoy your lightweight YouTube music player!
