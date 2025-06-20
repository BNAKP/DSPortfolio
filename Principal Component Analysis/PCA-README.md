# Principal Component Analysis

## Project Overview
Principal Component Analysis - Using PCA techniques for noise reduction and to remove background signals so an effective algorithm could be used to counteract sample drift effects from an Electron Microscopes measurement of the chemical composition of thermoelectrics

### Problem
The elemental quantification of a metal alloy sample is a simple process when using
an advanced analysis software such as Bruker Espirit. However even these programs fail to
incorporate key aspects of sample analysis such as drift correction and specific regional
selection, which if allowed for enable a more in-depth investigation of the material. Energy
dispersive x-ray spectroscopy (EDS) is a technique that produces a two-dimensional map of the
distribution of chemical elements on the surface of a sample. Recent developments now facilitate
the serial acquisition of a stack of such maps, collected as successive slices are removed from
the sample surface; these can then be processed post-acquisition to produce a three-dimensional
chemical map. The aim of this project was to improve 3d chemical mapping by (i) implementing
algorithms to reduce noise and remove background signal from individual spectra and (ii) correct
for sample drift effects. 

### Methodology

### Code

### Results
This method was successful in removing the noise components and
retaining the important data and allowed quantification via the Cliff-Lorimer method to be
performed. Comparison with Bruker quantification methods found the atomic percentage results
all agreed within 3% suggesting its accuracy was good in relation to comparable
software. While the discrepancies in values were mostly due to how accurately each method can
isolate and sum the spectra changes in quantification input specifications would allow for an
even closer accuracy with Bruker.
