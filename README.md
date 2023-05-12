# Instructions for Running Myrf_iCKO_OpticNerve snRNAseq Analysis
snRNA-seq Analysis of Demyelinating Myrf iCKO Optic Nerves

Katie Emberley 5.11.2023

Step 1: Download folders and files from GitHub as a zip folder and place it on your computer.

Step 2: Close R studio (if open) and then open the "Setup" RMD file and run each chunk in order. This will create a .here file and the file architecture below. This file architecture is critical for running the Rmd files. 

**Note** The output of command `here()` needs to retun the location of the "main" folder you unzipped from GitHub. 

For instance, if you place the main folder on your desktop, the `here()` command should return:
[1] "C: Users/emberley/Desktop/Myrf_iCKO_OpicNerve"

+ Myrf_iCKO_OpicNerve
+   Code/
    ++ Pre-processing
    ++ Analysis
    ++ Figures
  ++ GEO/
    ++ Cell Ranger/
       ++ PLP Cre Negative
       ++ PLP Cre Positive
       ++ Sox10 Cre Negative
       ++ Sox10 Cre Positive
   ++ ON dataset/
   ++ Outputs/
   ++ .here
   ++ Setup.RMD
   ++ ReadMe.md
   
Step 3: 
