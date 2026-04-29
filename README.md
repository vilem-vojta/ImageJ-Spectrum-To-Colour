# ImageJ-Spectrum-To-Colour
A custom plugin for ImageJ and Fiji that calculates the perceived sRGB colour directly from a measured emission spectrum (e.g., cathodoluminescence or photoluminescence) using standard CIE colorimetric principles. The calculated colour is then applied to the active greyscale image.

The plugin utilizes the CIE 1931 2-degree observer colour-matching functions (CMFs) spanning 360–830 nm. Both normalized and non-normalized spectra are accepted and automatically linearly interpolated onto the 1 nm CMF wavelength grid. Standard sRGB gamma correction for accurate display rendering is applied.

## Installation
1. Download the pre-compiled `Spectrum_To_Colour.jar` file from the Releases section on the right.
2. Copy the `.jar` file into the `plugins` folder located within your ImageJ or Fiji installation directory.
3. Restart ImageJ/Fiji. The plugin will automatically appear in the `Plugins` menu.

## Usage
1. Open your greyscale intensity map (e.g., CL or SE image) in ImageJ/Fiji.
2. Go to the menu bar and select `Plugins` > `Spectrum To Colour`.
3. A file dialog will appear. Select your spectrum `.csv` file.
4. The plugin will calculate the corresponding sRGB colour and apply it to the active image, preserving its original intensity gradients.

## Input File Format
The plugin requires a `.csv` file containing the emission spectrum. 
* Values must be separated by a semicolon (`;`).
* The first line (header) is ignored.
* The first column should contain the wavelength (in nm) and the second column the intensity.

**Example of a valid `.csv` structure:**
```text
# wavelength (nm);intensity
282.585022;0.008729516
283.011108;0.008598834
283.437225;0.008781788
283.863342;0.008677243
284.289459;0.008886333
```
