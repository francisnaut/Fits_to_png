## FITS File Processor

### Description
This Python script processes FITS files located in subdirectories of a given directory. It applies scaling limits, extracts statistics (like min, max, mean, etc.), and exports processed images into PNG and EPS formats using the DS9 tool. Additionally, statistics are saved into a `.txt` file.

### Graph Export Behavior
When exporting images with graphs (such as crosshairs or intensity graphs), the image is essentially a screenshot of the current view in the DS9 window. This means that the size of the exported image is directly related to the size of the DS9 display window.
If the DS9 window is too small or not properly zoomed in, the image may not be as clear or detailed. However, the script automatically applies a "zoom to fit" command to adjust the image display for the best fit before exporting. This ensures that the most appropriate zoom level is applied for each FITS file when exporting the image.
Therefore, the size and quality of the exported graph images depend on the DS9 window display settings at the moment of export.

### Usage

To run the script, use the following command in your terminal:

```bash
python fits_processor.py <directory_path> <scale_min> <scale_max>
```

Where:
- `<directory_path>`: Path to the folder containing FITS files.
- `<scale_min>`: Minimum scaling value for the image display.
- `<scale_max>`: Maximum scaling value for the image display.

Example:

```bash
python fits_processor.py ./data 0 1000
```

### Output
1. The script will display statistics (min, max, mean, etc.) for each FITS file and print them in a tabular format.
2. Images will be processed and exported as PNG and EPS files to the same directory as the FITS files.
3. A `.txt` file with the statistics for all the FITS files will be created in the same directory as the input folder, with the name `estadisticas_ds9_.txt`.


### Requirements
- Python 3.x
- Required Python libraries: 
  - `numpy`
  - `astropy`
  - `pyds9`
  - `tabulate`
  
Additionally, you will need the `ImageMagick` tool installed to convert `.eps` files to `.png`.

### Installation

To install the required Python libraries, run the following command:

```bash
pip install numpy astropy pyds9 tabulate
```

For `ImageMagick`, follow the installation guide for your operating system from [here](https://imagemagick.org/script/download.php).



