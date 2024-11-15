# AMP_FRESH_RV217_AcquisitionTimingPaper
The code and other support files associated with the Rossenkhan et al. paper re: infection timing estimation for AMP.

This software was originally run on 19 June 2020 as an operational step of the AMP trial sieve analysis.  This software is presented here as a historical archive of what was used in that moment, for the purposes of reproducibility.  Any use of this method in new research would be better accomplished with the "adtr" package, available here:

https://github.com/pedlefsen/adtr

## 1. System requirements

  This software was run on Ubuntu 18.04.5 LTS using R version 3.6.3 (2020-02-29)
  
  The specific R scripts and their required libraries are listed below.

  **0_support**

  Early files from what is now called the adtr package (in the directory tsic2) and the library file `tsic2_supplement.Rlib`:
    profvis

  **1_data_preparation**

  `amp_dx_history_preprocessing.R`:
    tidyverse

  **2_run_analysis**

  `run_weib3_idt.R`:
    tsic
    ggplot2 

## 2. Installation guide
  
  Install required version of R. 
  Install the tsic package:  https://github.com/philliplab/tsic
  Install other required R packages.
  Create local directories for code and data.
  
  Running the scripts requires configuring the "CONFIG" sections to map to the location of the files on your local filesystem.

## 3. Demo

  This software also requires the installation of the "tsic" package written by Philip Labuschagne, which is available here:
  
    https://github.com/philliplab/tsic

  All script files need to be properly pointed to the source of the input files and folders.  These path variables are indicated with the "CONFIG" tags in their comments.

  The names of the directories in this repository indicate the order in which the scripts should be run:

  **0_support**:  
  This directory contains code libraries required by these scripts,
  and includes an early (unreleased) version of the "adtr" package in
  the tsic2 subdirectory.  No code is run directly out of here.

  **1_data_preparation**:  
    `amp_dx_history_preprocessing.R`:  the script that processes the study file of lab test data.  This script takes only a few seconds to run, and generates all files required by the next two scripts.

  **2_run_analysis**:  
    `run_weib3_idt.R`:  the script that estimates the date of
    diagnosable acquisition using an R implementation of the method
    described in Grebe et al. 2019 (PMCID: PMC6815418  PMID: 31655566)
    and also/previously implemented as an online tool at
    https://tools.incidence-estimation.org/idt/.  This script takes
    30-60 minutes to run on a dataset the size of the AMP data, depending on your computer.

  From the command line starting in the code directory run the following commands:

    R CMD BATCH amp_dx_history_preprocessing.R &
    R CMD BATCH run_weib3_idt.R &

## 4. Instructions for use

  Same as demo instructions above.
  
