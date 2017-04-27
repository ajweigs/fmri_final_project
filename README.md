# fmri_final_project
Final project for Functional Neuroimaging Methods course at Washington University

### What is this repository for? ###

This repository contains a dataset from openfmri.org about functional brain activation in relation to the viewing of food images.
This project was completed for an undergraduate Functional Neuroimaging Methods course at Washington University in St. Louis.
A link to the dataset can be found here:

### How do I get set up? ###

To use these scripts, the user must first install MATLAB and SPM software. Once the data is downloaded, the user should use SPM's
save batch and script feature to create a jobfile for each preprocessing step. Our jobfiles are included in this repository and can
be adapted if the user changes the file paths to point to the user's own directory. Parameters for each processing step are included
at the bottom of the jobfile and can be changed according to the user's preferences.

Once the jobfile for each processing step has been created, the user should then use the CreateSPMJobfile function to create 
separate temporary jobfiles for each subject in the dataset. This function was written so as to replace any locations within the 
jobfile that referenced a given subject (e.g., 'sub-01'). These strings were replaced based on the indices for that string within
a given line, and therefore the user will have to change the indices within the if loops if these indices have been changed by
replacing the current directory in the filepath with the user's directory.

Once these indices have been replaced to reflect the user's jobfile, the user should then use the preprocessing functions (named
with an underscore func) to run the batch files through the spm jobman function, looping through each subject.
