# Image Format Converter with Optional Resizing

This Python script allows you to convert images into different formats (e.g., JPG, PNG, BMP) and optionally resize them. It uses a combination of multiprocessing for parallel processing of multiple images and multithreading for handling individual image format conversions.

## Features

- **Format conversion**: Convert images to formats like JPEG, PNG, BMP, and more.
- **Optional resizing**: Resize images during format conversion by specifying the desired width and height.
- **Parallel processing**: Leverages multiprocessing to process multiple images concurrently, speeding up the conversion process.
- **Multithreading**: Uses threads to handle individual image processing tasks.

## Prerequisites

- Python 3.x
- Required modules: `Pillow` for image processing and `argparse` for command-line argument parsing.

Install the required modules using:

```bash
pip install Pillow
```

To run the script, save it as `file_name` and make it executable:

```bash
chmod +x file_name
```

## How to Run

1. **Single Image Conversion**:

   ```bash
   ./file_name jpg path/to/image1.png
   ```

2. **Batch Conversion**:
   Convert multiple images at once:

   ```bash
   ./file_name png path/to/image1.jpg path/to/image2.bmp
   ```

3. **With Resizing**:
   Resize images while converting:
   ```bash
   ./file_name png path/to/image1.jpg --scale 800 600
   ```

## Command-line Arguments

- `output_format`: The desired output format (e.g., jpg, png, bmp).
- `input_image_paths`: One or more paths to the images to convert.
- `--scale`: Optional argument to resize the image to the specified width and height.

### Example

Convert and resize a single image from PNG to JPG with a resolution of 800x600 pixels:

```bash
./file_name jpg path/to/image.png --scale 800 600
```

Convert multiple images from PNG to BMP:

```bash
./file_name bmp path/to/image1.png path/to/image2.png
```
