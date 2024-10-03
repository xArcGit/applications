# Torrent Downloader

This is a simple Python-based torrent downloader using `libtorrent` for managing torrent sessions, and `multiprocessing` and `threading` to handle downloading and monitoring processes concurrently.

## Features:

- **Download Torrents**: Download torrent files with real-time progress updates.
- **Multiprocessing**: The torrent download is managed in a separate process.
- **Threading**: Progress updates are handled in a separate thread.
- **Colored Output**: The terminal output is color-coded for easier readability.

---

## Requirements:

1. **Python 3.6+**
2. **libtorrent**: You need to install `libtorrent`. You can install it via:

   ```bash
   pip install python-libtorrent
   ```

3. **PIL (optional)**: If your system needs to display logs in colored format, ensure that your terminal supports ANSI escape codes.

---

## How to Run:

To run the script, save it as `file_name` and make it executable:

```bash
chmod +x file_name
```

---

## How to Use:

1. **Basic Usage:**

   To start downloading a torrent, run the script with the path to the torrent file:

   ```bash
   ./file_name path_to_torrent_file
   ```

2. **Optional: Specify Download Directory**

   If you want to download files to a specific directory, use the `--download_dir` option:

   ```bash
   ./file_name path_to_torrent_file --download_dir /path/to/download_directory
   ```

---

## Sample Usage:

```bash
./file_name my_file.torrent --download_dir ~/Downloads
```

Output:

```bash
INFO: Starting download: my_file.torrent
INFO: 35.50% complete (down: 234.50 kB/s, up: 34.60 kB/s, peers: 15)
INFO: 98.20% complete (down: 154.34 kB/s, up: 20.20 kB/s, peers: 10)
INFO: Download complete: my_file.torrent
```

---

## Code Improvements:

1. **Error Handling**: Improved error handling with appropriate messages for invalid torrent files or connection failures.
2. **Graceful Exit**: The downloader now gracefully handles interruptions using `KeyboardInterrupt`.
3. **Concurrency**:
   - Downloading is handled by a separate process using `multiprocessing`.
   - Real-time monitoring of download progress is managed by a separate thread.
4. **Logging**:
   - Real-time status updates are logged, including percentage of completion, download/upload rates, and peer count.
   - All logging output is color-coded using ANSI escape sequences for better readability in terminals that support it.

---

## Dependencies:

- **libtorrent**: Manages torrent file handling.
- **multiprocessing**: Handles the download process in parallel with status monitoring.
- **threading**: Monitors download progress in real-time and prints status updates.

Install the dependencies via pip:

```bash
pip install python-libtorrent
```
