# Image Compressor

This is a simple Python script that converts JPEG and PNG images to WebP format and compresses them. It preserves the input directory structure and places the resulting files in an output folder.

## Requirements

- Python 3
- [Pillow](https://python-pillow.org/) library

Install dependencies with:

```bash
pip install Pillow
```

## Configuration

Edit the top of `compress.py` to set your input and output locations:

```python
BASE_DIR = os.path.dirname(os.path.abspath(__file__))

# folder containing images to process
INPUT_FOLDER = os.path.join(BASE_DIR, "folderName")  # change "folderName" as needed

# destination directory for converted images
OUTPUT_FOLDER = os.path.join(BASE_DIR, "output", "folderName")  # change output path if desired

MAX_WIDTH = 1200        # maximum width (pixels) before resizing
QUALITY = 75            # output quality for WebP
```

Place your images (jpg, jpeg, png) inside the directory referenced by `INPUT_FOLDER`.

## Usage

Run the script from the project root:

```bash
python compress.py
```

The script will walk through `INPUT_FOLDER`, convert supported images to WebP, resize them if they exceed `MAX_WIDTH`, and save them under `OUTPUT_FOLDER` while keeping the same subfolder structure. Progress and errors are printed to the console.

## Output

Converted and compressed WebP images will appear in the configured output directory.

## Notes

- You can adjust `MAX_WIDTH` and `QUALITY` constants in the script to tune compression settings.
- Ensure the output directory exists or let the script create it automatically.
- The script currently processes files with extensions `.jpg`, `.jpeg`, and `.png`.

---

Feel free to modify and extend this script for other formats or additional functionality.