# Principal Component Analysis

## Project Overview
Principal Component Analysis - Using PCA techniques for noise reduction and to remove background signals so an effective algorithm could be used to counteract sample drift effects from an Electron Microscopes measurement of the chemical composition of thermoelectrics

### Problem – Why I Did This Project
The aim of this project was to develop a method for aligning and analysing a stack of 2D elemental maps to enable accurate 3D compositional analysis of a metal alloy sample. While commercial software like Bruker Espirit can perform elemental quantification, it often lacks critical features such as drift correction and region-specific analysis. I set out to address these limitations by building a custom workflow that incorporated drift correction, noise reduction, and quantification using open-source tools and custom code. This approach allowed for a more detailed and accurate investigation of the material’s internal structure and composition.

### Method – How I Tackled the Problem
I began by loading SEM and EDS datasets into Python, excluding the EBSD component due to its size. Drift correction was performed using the Hyperspy library, enhanced with my own preprocessing steps including Sobel and Hanning filters to improve edge detection and alignment accuracy. Cross-correlation was used to calculate shift vectors, and these were applied to both SEM and EDS data. I then cropped the EDS data to retain only overlapping regions across slices. Noise reduction was achieved through Principal Component Analysis (PCA) followed by Non-negative Matrix Factorisation (NMF), which preserved only the meaningful spectral components. Finally, I prepared the data for quantification using the Cliff-Lorimer method, incorporating background subtraction and integration windows tailored to each element’s emission lines.

### Code – Tools and Algorithms I Used
The analysis was implemented in Python using a combination of open-source libraries and custom scripts. Key components included:

Data Handling and Preprocessing:

- Used the Hyperspy library to load and manipulate SEM and EDS datasets.
- Applied Sobel and Hanning filters to enhance edge detection and improve alignment accuracy.
- Cropped EDS data interactively to retain only overlapping, data-rich regions.

Drift Correction:

- Employed cross-correlation to calculate shift vectors between image slices.
- Applied these vectors to both SEM and EDS data using a “roll” technique to preserve data integrity.

Noise Reduction:

- Performed Principal Component Analysis (PCA) to estimate the number of significant components.
- Passed selected components through Non-negative Matrix Factorisation (NMF) to isolate signal from noise while ensuring all values remained physically meaningful (non-negative).

Quantification:

- Prepared metadata for each element, including expected x-ray lines and background windows.
- Used the Cliff-Lorimer method to calculate atomic percentages based on peak intensities and k-factors.
- Carefully defined integration windows to avoid overlapping peaks and ensure accurate quantification.

Visualisation and Validation:

- Developed tools to visualise alignment quality, spectral clarity, and 3D elemental distributions.
- Compared results with Bruker software to validate accuracy and highlight areas where the custom method offered improved insight (e.g. detection of metal oxides).

[This code is University property and so i am unable to provide the raw data or code]

### Result – What I Found
This project successfully produced an algorithm capable of aligning, denoising, and quantifying SEM and EDS data with high accuracy. Visual inspection confirmed the effectiveness of the alignment, and the noise reduction significantly improved spectral clarity. The quantification results closely matched those from Bruker software, with all elemental percentages agreeing within 3%. My method also detected metal oxides and subtle compositional variations that Bruker missed. The 3D visualisation revealed distinct alloy phases and compositional gradients, particularly between milled and unmilled regions. These findings demonstrated that the custom workflow not only matched but in some aspects exceeded the capabilities of existing commercial solutions.
