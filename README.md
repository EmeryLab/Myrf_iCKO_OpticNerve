# Instructions for Running Myrf_iCKO_OpticNerve snRNAseq Analysis
snRNAseq Analysis of Demyelinating Myrf iCKO Optic Nerves
This repository can be used to exactly reproduce the snRNAseq analysis done for the current publication.

Katie Emberley 10.19.2023  

## System Requirements
The snRNAseq Analysis was preformed using R version 4.2.1 (2022-06-23) -- "Funny-Looking Kid"
Copyright (C) 2022 The R Foundation for Statistical Computing
Platform: x86_64-apple-darwin17.0 (64-bit)

The analysis pipeline can be conducted on any computer capable of using the "RStudio" application. 

## snRNAseq Analysis Reproduction
### Create File Structure and Download the Rmd files 
The download will take aprox. 1hr.

Step 1: Download folders and files from GitHub as a zip folder and place it on your computer.

Step 2: Close R studio (if open) and then open the "Setup" RMD file and run each chunk in order. This will create a .here file and the file architecture below. This file architecture is critical for running the Rmd files. 

**Note** The output of command `here()` needs to retun the location of the "main" folder you unzipped from GitHub. 

For instance, if you place the main folder on your desktop, the `here()` command should return:
[1] "C: Users/emberley/Desktop/Myrf_iCKO_OpicNerve"

+ Myrf_iCKO_OpicNerve/
    * Code/
        * Pre-processing/
        * Analysis/
           * DEG Code/
           * Microglia Subclustering Code/
           * Oligolineage Subclustering Code/
        * Figures/
  * GEO/
    * Cell Ranger/
   * Outputs/
      * DEGs/
      * Intermediate Objects/
      * QC Objections/
      * Subclusters
   * .here
   * Setup.RMD
   * ReadMe.md
   
Step 3: From GEO (GSE243788) download and place Cell Ranger output folders into the folder

".../GEO/Cell Ranger" 

Two files for every sample needed are the: `filtered_feature_bc_matrix.h5` and the `raw_feature_bc_matrix.h5` (total of 16 files). 

### Run the snRNAseq Pipeline 
Step 4: Open RMD File "Sequential Knit Pre-Processing and Analysis Files.Rmd" in main folder and run the chunk to knit all of the files. The pre-processing files must be knit first, then the "subsetting and integration". After that, the remaining files are optional. If you would rather run the files individually, follow the same sequence:

+ Pre-processing code found in folder: ".../Code/Pre-processing" : Run RMD files in order (1-8)
+ Integration and Subsetting can be found in folder: ".../Code" : Run RMD File "ON Integration and Subsetting.Rmd"

If you knit the files or if you run individually, all objects and RData will be placed in ".../Outputs". Outputs contain the subfolders:

+ QC Objects (objects created from running the pre-processing files with each replicate indivdiually processed before merging)
+ Intermediate Objects (objects created during integration following computationally heavy tasks. These are not final objects)
+ Subclusters (objects created following the integration of the replicates that subsets individual clusters into their own object e.g. Microglia)
+ DEGs (differentially expressed genes for cluster identification and between genotypes)

## Interactive Viewing Option
A user-friendly Shiny App is available at https://emerylab.shinyapps.io/Myrf_iCKO_OpticNerve/ where users can look at gene expression across our dataset without needing to code anything. 
