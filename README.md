#  Vectorial PSF Generator for Light Sheet Microscopy

This script simulates a **vectorial detection PSF** combined with a **Gaussian excitation profile** in Z to produce an effective 3D PSF for use in deconvolution.

---

## What It Does

- Simulates a **vectorial detection PSF** using numerical parameters.
- Models a **Gaussian light sheet** excitation profile in the Z-axis.
- Multiplies both to get the **effective PSF**.
- Normalizes and saves the result as a 32-bit TIFF.

---



###  Optical Setup

| Parameter     | Description                                | Value (default)      |
|--------------|--------------------------------------------|----------------------|
| `wavelength` | Emission wavelength (e.g. eGFP)            | `0.525 µm`           |
| `NA`         | Numerical Aperture of detection objective  | `1.1`                |
| `ni`         | Refractive index of immersion medium       | `1.333` (water)      |
| `ns`         | Refractive index of the sample             | `1.45`               |

### 📐 PSF Grid

| Dimension     | Description                    | Value |
|---------------|--------------------------------|-------|
| `nx`          | Lateral (X/Y) size (odd number)| `65`  |
| `nz`          | Axial (Z) size (odd number)    | `33`  |
| `dxy`         | Lateral pixel size (µm)        | `0.347` |
| `dz`          | Z-step (µm)                    | `2.0` |
| `pz`          | Point source Z-position        | `0.0` (focus) |

### Excitation Model

- Light sheet is modeled as a **Gaussian beam** in Z.
- Full Width at Half Maximum (FWHM): `3.0 µm`

---

##  Dependencies

Install required Python packages:

pip install psfmodels numpy tifffile
