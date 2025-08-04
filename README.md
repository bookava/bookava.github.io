# Bookava Audiobook Player

**Bookava** is a modern, browser-based audiobook player designed for simplicity and power. It runs entirely on the client-side as a Progressive Web App (PWA), meaning your files are never uploaded to a server. You can "install" it on your device for an offline, app-like experience. Just open the app, drop your audiobooks, and enjoy seamless listening with robust features and automatic progress saving.

## ✨ Key Features

*   **Progressive Web App (PWA)**: Install Bookava on your desktop or mobile device for a native-app feel. It works offline, making it the perfect companion for listening on the go.
*   **Serverless & Private**: Runs 100% in your browser. Your files are processed locally and never uploaded, ensuring complete privacy.
*   **Drag & Drop Simplicity**: Easily start a session by dragging and dropping your audio files, a single `.zip` archive, or an `.m4b` file.
*   **Comprehensive Format Support**:
    *   Plays standard audio formats: `.mp3`, `.wav`, `.ogg`, `.m4a`, and `.flac`.
    *   Dedicated **`.m4b` Audiobook Support**: Automatically parses and displays chapter markers from `.m4b` files for easy navigation.
*   **Automatic Progress Saving**: The player automatically saves your progress (current track, time, volume, and playback speed) in your browser's `localStorage`.
*   **Smart Session Resume**: When you reopen a book, Bookava prompts you to continue exactly where you left off, restoring all your settings.
*   **Bookshelf History**: Your recent audiobooks are saved to a beautiful, interactive bookshelf for quick access to your library.
*   **Advanced Playback Controls**:
    *   Variable playback speed from **0.5x to 16.0x**.
    *   **Auto-Acceleration**: Optionally increases speed by 0.1x every 10 minutes.
    *   Quick seek buttons (`-15s` / `+15s`).
    *   Full playlist view with chapter navigation.
*   **Keyboard Shortcuts**: Control playback without your mouse:
    *   `Spacebar`: Play/Pause
    *   `ArrowRight`: Seek forward
    *   `ArrowLeft`: Seek backward
*   **Light & Dark Themes**: Switch between a sleek dark mode and a clean light mode to suit your preference.
*   **Metadata & Artwork Extraction**: Automatically reads metadata (title, album) and cover art from your files to provide a rich user experience.
*   **Fully Responsive Design**: A clean, minimalist UI that looks and works great on both desktop and mobile devices.
*   **No Installation Needed**: Runs instantly in any modern browser. No complex setup or build process required.

## 🚀 How to Use

Getting started with Bookava is incredibly simple.

**1. Open the Player**
Since it's a PWA, you can host the files on a simple web server (like GitHub Pages) or run them locally. When you first visit the URL in a modern browser, you'll be prompted to **"Install"** or **"Add to Home Screen"**. This will add Bookava to your device just like a native app.

**2. Load Your Audiobook**
You have two options:
*   **Drag & Drop**: Drag your audio files (e.g., `chapter1.mp3`), a `.zip` file, or a single `.m4b` file onto the upload zone.
*   **Click to Select**: Click the "Choose Audiobook" button to open a file selection dialog.

**3. Enjoy Listening**
The player will process your files, build a playlist, and start playing. Your progress is saved automatically, so you can close the app and resume later by re-loading the same audiobook.

## 🛠️ Technical Stack

This project is built with a focus on simplicity and performance, using pure web technologies without any frameworks.

*   **Core Technology**: HTML5, CSS3 (with CSS Variables for theming), and **Vanilla JavaScript (ES6+)**.
*   **PWA Functionality**:
    *   **Service Worker (`sw.js`)**: Manages caching of app assets for a true offline-first experience.
    *   **Web App Manifest (`manifest.json`)**: Defines the app's metadata, icons, and display properties for installation.
*   **Client-Side Libraries**:
    *   [**`zip.js`**](https://gildas-lormeau.github.io/zip.js/): Handles the client-side unzipping of `.zip` archives.
    *   [**`jsmediatags`**](https://github.com/aadsm/jsmediatags): Reads ID3 tags (metadata and cover art) from audio files.
    *   [**`CryptoJS`**](https://cryptojs.gitbook.io/docs/): Used to generate a unique hash from file details to serve as a reliable ID for each audiobook, enabling robust history and state management.

## 🧠 Code Highlights & Logic

*   **State Management**: The player's state is managed via `localStorage`. A unique ID is generated for each audiobook based on a hash of its file details, allowing the state to be reliably associated with the correct book.
*   **PWA Lifecycle**: The service worker (`sw.js`) ensures that the application shell is cached on install, allowing the app to load instantly and run even without an internet connection.
*   **M4B Chapter Parsing**: The application includes logic to parse the `chap` atom within an `.m4b` file container, extracting chapter start times and titles to dynamically build the playlist.
*   **Client-Side File Handling**: The application leverages the browser's `File API` and `URL.createObjectURL()` to handle files locally. This is memory-efficient and fast, as it avoids reading entire files into memory.
*   **Dynamic UI**: The entire user interface is handled with pure JavaScript DOM manipulation for a lightweight and responsive experience.

## 📄 License

This project is licensed under the **MIT License**.
```
