# Timeless Tunes

## Preview
<img src="https://raw.githubusercontent.com/itsadityakr/timeless-tunes-music-player/refs/heads/main/css/assets/gif.gif" alt="" width="700">

## Project Overview

The Advanced Music Player is a web-based application that allows users to play music, view song details, adjust volume, and switch themes. It features a clock and a motivational quote, with additional functionalities for microphone control and volume adjustment.

## File Structure

- **HTML**:
  - `index.html`: Main HTML file.

- **CSS**:
  - `style.css`: Main stylesheet for the player.
  - `themes/light-mode.css`: Stylesheet for the light mode theme.
  - `hover.css`: Stylesheet for hover effects.

- **JavaScript**:
  - `script.js`: Main script for music player functionality.
  - `music-list.js`: Script for managing the music list.
  - `theme-switch.js`: Script for toggling themes.
  - `speech.js`: Script for microphone control.
  - `clock.js`: Script for displaying the clock and date.

## HTML Structure

### Head Section

- Meta tags for character set, compatibility, and viewport settings.
- Title: "Timeless Tunes".
- Link tags for stylesheets, including Google Fonts and Font Awesome icons.

### Body Section

- **`<div class="clock-container">`**: Displays the current time, date, and a motivational quote in Hindi.
- **`<div class="player">`**: Main container for the music player.
  - **`<div class="wrapper">`**: Contains all elements of the player.
    - **`<div class="main">`**: Displays the logo with a music icon.
    - **`<div class="top-bar">`**: Contains the dark mode toggle, "Now Playing" text, and mic toggle button.
    - **`<div class="img-area">`**: Displays the album cover image.
    - **`<div class="song-details">`**: Displays the song name and artist.
    - **`<div class="progress-area">`**: Contains the progress bar and song timer.
    - **`<audio>`**: Main audio element.
    - **`<div class="volume">`**: Controls volume with a range input and volume icon.
    - **`<div class="controls">`**: Contains controls for play/pause, previous, next, repeat, and music list.
    - **`<div id="wave">`**: Visual representation of music waves.
    - **`<div class="music-list">`**: Displays the list of songs.
      - **`<div class="header">`**: Header for the music list with a close button.
      - **`<ul>`**: Unordered list for dynamically adding music items.

## JavaScript Functionality

### Key Variables

- **Selectors for DOM Elements**:
  - `wrapper`, `musicImg`, `musicName`, `musicArtist`, `playPauseBtn`, `prevBtn`, `nextBtn`, `mainAudio`, `progressArea`, `progressBar`, `musicList`, `moreMusicBtn`, `closemoreMusic`, `recent_volume`, `volume_show`, `wave`.

- **Music Data**:
  - `allMusic`: Array containing information about all available songs.
  - `musicIndex`: Index of the currently playing song.
  - `isMusicPaused`: Boolean flag to check if music is paused.

### Event Listeners

- **Window Load Event**: Loads a random song and updates song details.
- **Play/Pause Button**: Toggles between play and pause states.
- **Previous/Next Buttons**: Navigates to previous or next songs.
- **Progress Area Click**: Updates the current time of the song based on the click position on the progress bar.
- **Repeat Button**: Toggles between repeat, repeat one, and shuffle modes.
- **Audio Ended Event**: Handles song end based on the repeat/shuffle mode.
- **More Music Button**: Toggles the display of the music list.

### Functions

- **`loadMusic(indexNumb)`**: Loads song details based on index.
- **`playMusic()`**: Plays the current song and updates UI.
- **`pauseMusic()`**: Pauses the current song and updates UI.
- **`prevMusic()`**: Navigates to the previous song and plays it.
- **`nextMusic()`**: Navigates to the next song and plays it.
- **`playingSong()`**: Highlights the currently playing song in the playlist.
- **`clicked(element)`**: Plays the song corresponding to the clicked element in the playlist.
- **`mute_sound()`**: Mutes the audio and updates the volume display.
- **`volume_change()`**: Adjusts the volume based on user input.

### Song Progress and Duration

- **`timeupdate` Event**: Updates the progress bar and current time display.
- **`loadeddata` Event**: Sets the total duration of the song.

### Repeat and Shuffle Functionality

- **Repeat Button Click Event**: Cycles through repeat, repeat one, and shuffle modes.
- **Audio Ended Event**: Determines the next action based on the repeat mode:
  - `repeat`: Plays the next song.
  - `repeat_one`: Repeats the current song.
  - `shuffle`: Plays a random song.

### Music List Management

- **Generating Playlist**: Creates list items for each song in `allMusic`.
- **Playlist Click Event**: Plays the selected song from the list.

### Volume Control

- **Mute Function**: Sets the audio volume to zero.
- **Volume Change Function**: Adjusts the audio volume based on user input.

### Sample Music Data (`allMusic` Array)

Contains objects with:
- `name`: Name of the song.
- `artist`: Artist of the song.
- `img`: Filename of the album cover image.
- `src`: Filename of the song.

## Speech Recognition

### Initialization

- **`recognizing`**: Boolean flag indicating if speech recognition is active.
- **`recognition`**: Instance of `webkitSpeechRecognition`.

### Configuration

- `recognition.continuous = true;`: Allows continuous speech recognition.

### Event Handlers

- **`recognition.onstart`**: Sets `recognizing` to true when speech recognition starts.
- **`recognition.onresult`**: Processes speech recognition results.
- **`recognition.onerror`**: Logs errors during speech recognition.

### Voice Commands

- **`play music`**: Calls `playMusic()`.
- **`pause music`**: Calls `pauseMusic()`.
- **`previous music`**: Calls `prevMusic()`.
- **`next music`**: Calls `nextMusic()`.
- **`mute sound`**: Calls `mute_sound()`.
- **`change volume to [value]`**: Adjusts volume with `changeVolume(value)`.

### Toggle Microphone

- **`toggleMic()`**: Starts or stops speech recognition.

### Change Volume

- **`changeVolume(value)`**: Updates volume display and sets audio volume.

## Dark Mode and Theme Toggle

### Initialization

- **`darkModeToggle`**: DOM element for the dark mode toggle button.
- **`currentTheme`**: Retrieves the stored theme from localStorage.

### Set Initial Theme

- **`setTheme(themeName)`**: Updates the theme by setting the href attribute of the `<link>` element with ID `theme`.

### Theme Switching Logic

- Light mode and dark mode stylesheets are toggled based on user interaction.

### Event Listener for Theme Toggle

- Adds a click event listener to the dark mode toggle button to cycle through themes.

---

- by Aditya Kumar
- Do not forget to give credits.