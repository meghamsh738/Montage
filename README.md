# Montage Creator Script

This project contains a Jython script for ImageJ/Fiji that generates a montage from a multi-channel image, applies calibration, draws scale bars, and adds the original image title.

## Usage

1. Open an image in [Fiji](https://imagej.net/software/fiji/).
2. Run the script with the Fiji Jython interpreter (`Plugins > New > Script`).
3. The script will:
    - Duplicate your image,
    - Apply calibration,
    - Split and merge channels,
    - Add scale bars,
    - Create a montage,
    - Annotate with the image title.

## Script

See [montage_creator.py](montage_creator.py).

---

### Requirements

- [Fiji/ImageJ](https://imagej.net/software/fiji/) with Jython support.

---

