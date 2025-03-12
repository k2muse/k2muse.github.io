---
layout: page-fullwidth
title: "Data Usage"
subheadline: "K2MUSE Dataset"
teaser: "We have experimented with several machine learning models on the dataset and provided scripts and code for utilizing the dataset."
permalink: "/usage/"
header: no
---
<div class="panel radius" markdown="1">
**Table of Contents**
{: #toc }
*  TOC
{:toc}
</div>



## Environment

Installation and Configuration Requirements:  
* [Biomechanics ToolKit (BTK)](https://biomechanical-toolkit.github.io/docs/): Required for parsing "*.c3d" files in MATLAB.
* [Jupyter Notebook](https://jupyter.org/): Needed to open and run "*.ipynb" scripts.
* [MATLAB 2022b](https://www.mathworks.com/products/matlab.html): Used for data visualization and processing.
* [Python 3.8](https://www.python.org/): Required for running Python-based scripts and models.

For MATLAB scripts, we use MATLAB (version 2022b).

For Python scripts, we use Visual Studio Vode (version 1.98.1).

The processed file is of *.mat format and can be opened using MATLAB (version 2022b, MathWorks, Natick, MA, USA).

To do so in your MATLAB workspace, use the load command and the full file extension: `load('you path of *.mat')`​.

You can also open the \*.mat files by double-clicking them directly. Please note that the files are large and may take some time to open, so please be patient.



## Load and Segment

This script is used to read and parse raw data from SourceData. The loading of all modal data and gait normalization are processed through the MATLAB script “scriptProcess.mlx”.

The parsing of "\*.c3d" files is achieved using the [Biomechanics ToolKit (BTK)](https://biomechanical-toolkit.github.io/docs/).

The specific introduction of this script is as follows:

* Readme:

  User guide for this script.

* Clear All:

  Initialize the working environment by clearing variables, closing windows, etc.

* Part1. Variable Definition:

  * Step1. For Path Definition:

    Define the storage path for the data.

  * Step2. For Data Processing:

    Define the variables needed during the file processing, including participant ID, device acquisition frequency, etc.

* Part2. Load Multimodal Data:

  Parse the data collected from each device in the 'SourceData' folder and save it to a unified '\*.mat' file.

  * Step1. Process Vicon Data

    * Load and Segmentation

      Parse the kinematics, dynamics, and gait events from the '\*.c3d' files in the 'Vicon' folder, perform gait normalization based on heel strike, and then save the data in '.mat' format to the 'ViconProcessed' folder.

  * Step2. Process ELONXI Data

    * Load and Segmentation

      Obtain the AUS data from the '\*.txt' files in the 'ELONXI' folder, merge the data from each channel, divide it based on gait events, and then save the data in '.mat' format to the 'ELONXIProcessed' folder.

    * Merge ELONXI to Vicon.mat (From ViconProcessed, save to DataMergeELONXI)

      Extract data from the 'ViconProcessed' folder and merge it with the AUS data. Save the merged data in '.mat' format to the 'DataMergeELONXI' folder.

  * Step3. Process Noraxon Data

    * Load and Segmentation

      Obtain the sEMG data from the '.mat' files in the 'Noraxon' folder, divide it based on gait events, and then save the data in '.mat' format to the 'NoraxonProcessed' folder.

    * Merge Noraxon to Vicon.mat (From DataMergeELONXI, save to DataProcessed)

      Extract data from the 'DataMergeELONXI' folder and merge it with the sEMG data. Save the merged data in '.mat' format to the 'DataProcessed' folder.



## Plot kinematics and kinetics

The MATLAB script "scriptPlot.mlx" can extract data for all participants from "ViconProcessed," save it as 'figData,' and plot the kinematics and kinetics.

The specific introduction of this script is as follows:

* Readme:

  User guide for this script

* Clear All:

  Initialize the working environment by clearing variables, closing windows, and other necessary tasks.

* Part1. Variable Definition:

  * Step1. For Path Definition:

    Define the storage path for the data.

  * Step2. For Figure Parameter:

    Define the parameters required for plotting the figures.

* Part2. Figures In Manuscript

  * Step1. Load 'figData':

    Load 'figData.mat' from "FigureData" folder for plotting figures.

  * Step2. Figures: Ideal Condition:

    Plot the kinematics and dynamics of all participants under different ramps and speeds in the ideal condition experiment.


## Angle Regression

* Readme:
  
  User guide for this code.

* Part1. Import Module:
  
  Import the necessary libraries and custom modules for data processing, modeling, and plotting.

* Part2. Definition

  * Step1. Define Path:

    Define the paths for data, results, H5 files, and image storage, and create the corresponding folders.

  * Step2. Define Variables:

    Define the variables needed in the data processing and model fitting processes.

* Part3. ML Model

  Process the data, including loading, preprocessing, feature extraction, etc., and train and evaluate different machine learning models to predict joint angles.

* Part4. Analysis Results

  Calculate the metrics for all participants and plot the mean and standard deviation of the corresponding metrics.

  * Step1. Calculate Results:

    Calculate the average and standard deviation of the results for all participants.

  * Step2. Fig: RMSE-Bar:

    This step creates a bar plot to visualize the RMSE (Root Mean Squared Error) of joint angles for different models and joints.





## Know Issues

* The Nexus software detected incorrect gait events for some experiments. These errors were manually corrected using the [open-source software Mokka](https://biomechanical-toolkit.github.io/mokka/index.html).
* Some trials from certain participants contained defective data due to an investigator error, which was later re-collected.
* Some participants have insufficient AUS data frames for certain trials, which results in empty AUS data for some strides in the NormalizedData.



