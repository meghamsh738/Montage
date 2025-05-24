
# 🧬 ImageJ Macro – Safe RGB Montage Generator with Scale Bar & Title

## 📋 Description

This ImageJ macro script automates the process of creating a clean, publication-ready montage from a multichannel image. It includes:

* **Calibration-aware** processing — only sets pixel size (0.2 µm) if missing
* **Channel splitting** and re-merging into RGB composite
* **Scale bar** drawing on each slice
* **Montage** generation (5 columns × 1 row)
* **Title annotation** below the final image
* **Automatic cleanup** of intermediate images

This is ideal for confocal max projections or other fluorescence images needing standardized presentation.

---

## 🔧 What It Does (Step-by-Step)

1. **Duplicates** your active image to preserve the original
2. **Applies calibration** of 0.2 µm/pixel **only if the image is uncalibrated**
3. **Splits RGB channels** and re-merges them into a new composite
4. **Flattens** and stacks the channels
5. Adds a **50 µm scale bar** (bottom-right corner) to each slice
6. Creates a **5×1 montage**
7. **Extends the canvas** downward and adds the original image title below
8. **Cleans up** intermediate duplicates and stacks

---

## ⚙️ Usage Instructions

### 🔹 Ideal Workflow for Confocal Images:

1. Open your **max-projected images**
2. Set consistent **brightness/contrast** using ImageJ and apply to all
3. Run this script on each image:

   * Copy final montage (`Edit → Copy to System`)
   * Paste into PowerPoint or figures
   * **Close previous montage window** before running again

---

## 🔄 Calibration Handling

This script will:

* ✅ **Apply `0.2 µm/pixel` calibration** **only if** image is uncalibrated (1.0 pixel width/height and unit is `"pixel"`)
* ✅ **Preserve existing calibration** if already present

This ensures you don’t accidentally misrepresent scale when working with images from different sources.

---

## 🖼️ Output

* **5-panel horizontal montage**: 3 individual channels, 1 RGB composite, and a final (optional/empty) panel
* **Scale bar**: 50 µm length, 5 px height, bold white in the lower right
* **Title**: Original image title drawn in bold black font below the image

---

## ⚠️ Notes

* Make sure your montage **window is closed** before running the script on the next image to avoid errors.
* If working with **multiple images**, consider adapting the script for batch processing.
* The **composite image** is created after channel merge, so channel order matters — ensure proper assignment (e.g., red → c1, green → c2, blue → c3) if manually assigning.

---

## 🧰 Customization Table

| Feature        | Line in Script       | How to Customize                           |
| -------------- | -------------------- | ------------------------------------------ |
| Calibration    | `if cal.pixelWidth…` | Change default pixel size if needed        |
| Scale Bar      | `width=50 height=5`  | Adjust scale bar size and location         |
| Montage Layout | `columns=5 rows=1`   | Change panel layout (e.g., 3×2 grid)       |
| Font/Title     | `Font.BOLD, 70`      | Change font size or type for the title     |
| Canvas Padding | `pad = 50`           | Adjust space for the title below the image |

---

