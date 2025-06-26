# PSF_lightsheet

This code simulates and saves the effective point spread function (PSF) for a light sheet microscope (LSM) with vectorial detection and Gaussian excitation in the Z direction.

Key Steps:
Import Libraries:
Loads psfmodels (for PSF simulation), numpy, tifffile, and Path for file handling.

Set Acquisition Parameters:
Defines the emission wavelength, image size (nx, nz), pixel sizes (dxy, dz), and the position of the point source (pz).

Define Microscope/Detection Parameters:
Sets the objective numerical aperture (NA), immersion medium refractive index (ni), and sample refractive index (ns).

Simulate Vectorial Detection PSF:
Uses psfm.vectorial_psf_centered to compute the 3D detection PSF based on the above parameters.

Model Light Sheet Excitation Profile:
Models the excitation (illumination) profile as a Gaussian in Z, with a specified full width at half maximum (fwhm_exc_z).

Combine Excitation and Detection:
Multiplies the detection PSF by the excitation profile to get the effective PSF for the light sheet microscope, then normalizes it.

Save the Effective PSF:
Writes the resulting 3D PSF as a TIFF file to the specified output directory.
