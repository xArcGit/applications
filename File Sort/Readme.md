# File Organizer Script

## Overview

This Python script helps organize files in your `~/downloads` directory into predefined categories such as documents, pictures, PDFs, videos, music, and more. It moves files to appropriate directories based on their extensions, deletes hidden files, and handles directories separately. It uses parallel processing to ensure efficiency, leveraging both multithreading and multiprocessing.

## Features

- **File categorization**: Files are moved to directories such as `document`, `picture`, `pdf`, etc., based on their file extensions.
- **Hidden files handling**: Hidden files (such as `.env` and `.gitignore`) are deleted by default.
- **Directory management**: Directories in the source folder are moved to a designated `folder` directory.
- **Parallel processing**: The script uses both multiprocessing (for processing chunks of files) and multithreading (for processing individual files within chunks) to improve performance.
- **Logging**: Errors encountered while moving files are logged in the `~/.errors` directory with a timestamped log file.

## File Structure

- **Source Directory**: `~/downloads`
- **Destination Directories**:
  - `~/document`
  - `~/picture`
  - `~/pdf`
  - `~/text`
  - `~/music`
  - `~/video`
  - `~/edit`
  - `~/archive`
  - `~/code`
  - `~/hidden`
  - `~/other`
  - `~/torrent`
  - `~/folder`

## How It Works

1. **Identify file types**: Files in the source directory (`~/downloads`) are classified based on their file extensions.
2. **Move files**: Files are moved to their corresponding directories (e.g., `.jpg` files are moved to `~/picture`).
3. **Handle hidden files**: Files that match specific hidden file types (e.g., `.env`, `.gitignore`) are deleted.
4. **Process directories**: Any directories in the source folder are moved to the `~/folder` directory.
5. **Parallel execution**: The script uses `ProcessPoolExecutor` for multiprocessing and `ThreadPoolExecutor` for multithreading.

## Prerequisites

- Python 3.x
- Modules: `os`, `shutil`, `logging`, `concurrent.futures`, `dataclasses`, `multiprocessing`, `threading`, `datetime`

## How to Run

1. Clone the repository or download the script.
2. Install the required Python modules.
3. To run the script, save it as `file_name` and make it executable:
   ```bash
   chmod +x file_name
   ```
4. Run the script:
   ```bash
   ./file_name
   ```

## Customization

You can modify the `source_dir` and `destination_dirs` variables to change the source directory or target directories for file types.

You can also add new file types to the `file_types` dictionary to handle new file extensions.

## Logging

Errors that occur during file operations (moving, deleting) are logged in the `~/.errors` directory, with a timestamped log file created for each run of the script.

## Future Improvements

- Add configuration options to customize file categorization without editing the script.
- Implement dry-run mode to preview changes before moving files.
- Add support for user-defined file extensions and categories via a config file.
