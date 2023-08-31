# ACCESS-NRI Training Day 4 September 2023

This repository includes the material for the <a href="https://www.access-nri.org.au" target="_black">ACCESS-NRI</a> <a href="https://www.access-nri.org.au/event/access-training-day-2023/" target="_black">Training Day</a> on 4 September 2023.  
You can find a general overview of the ACCESS-NRI documentation on the <a href="https://access-hive.org.au" target="_blank">ACCESS-Hive</a>.  

This repository is structured according to the <a href="https://www.access-nri.org.au/access-training-day-program/" target="_blank">Training Day program</a>:

1. [Running ACCESS models and Rose/cylc in ARE](#1-running-access-and-rosecylc-in-are)  
2. [Finding and Loading Model Data with Intake](#2-introduction-to-the-access-nri-intake-catalog)  
3. [Model Evaluation with ILAMB (International Land Model Benchmarking)](#3-model-evaluation-with-ilamb-international-land-model-benchmarking)
4. [Model Evaluation with ESMValTool](#4-model-evaluation-with-esmvaltool)

We value your feedback on this training, in-person or via the <a href="https://forum.access-hive.org.au/" target="_blank">ACCESS-Hive Forum</a>, as it will help us to provide better training and documentation for the ACCESS community on our documentation portal, <a href="https://access-hive.org.au" target="_blank">ACCESS-Hive</a>.

## Cloning this repo

To do the training on Intake, ILAMB and ESMValTool, you will need to clone a local copy of this repo to Gadi as follows: 

1. Log in to Gadi via the command line using your NCI username and password.

   ```bash
   ssh <your_nci_username>@gadi.nci.org.au
   ```
   
2. Clone this Github repo to your user directory within `/scratch/nf33` on Gadi. Depending on whether or not you've used the nf33 project before, your user directory may or may not already exist.

   ```bash
   mkdir -p /scratch/nf33/$USER
   cd /scratch/nf33/$USER
   git clone https://github.com/ACCESS-NRI/workshop-training-2023.git
   ```

## 1. Running ACCESS and Rose/cylc in ARE  

This exercise and its [training material](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/access_rose_cylc/rose_cylc_example.md) will walk you through the setup of an [ACCESS Coupled Model 2 (ACCESS-CM2)](https://access-hive.org.au/models/configurations/access-cm/) model run.

## 2. Introduction to the ACCESS-NRI Intake catalog

This exercise will teach you how to use the ACCESS-NRI Intake catalog to discover, load and share ACCESS and ACCESS-related data.

To run this exercise, you need to be a member of the following NCI projects:
```
nf33, dk92, fs38, p73, xp65, hh5 (optional)
```

The exercises are split in two parts to be run via an ARE JupyterLab session:

1. [Jupyter notebook exercise part 1](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/intake/Intake_tutorial_p1.ipynb): using the ACCESS-NRI Intake catalog​

2. [Jupyter notebook exercise part 2](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/intake/Intake_tutorial_p2.ipynb): creating Intake-ESM datastores for ACCESS output​

The ACCESS-NRI Intake Catalogue is curated by ACCESS-NRI with further information on its <a href="https://access-nri-intake-catalog.readthedocs.io/en/latest/index.html" target="_blank">documentation website</a> and <a href="https://access-hive.org.au/model_evaluation/model_evaluation_model_catalogs" target="_blank">this ACCESS-Hive page</a>.

## 3. Model Evaluation with ILAMB (International Land Model Benchmarking)

This exercise and its [training material](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/ilamb/ILAMB_training.md) will walk you through the evaluation of models and confrontation with observational data using ILAMB.

To run this exercise, you need to be a member of the following NCI projects:
```
nf33, xp65, hh5, ct11, oi10, fs38 
```

You can find the expected results of this exercise in this <i>Gadi</i> directory:
```
/g/data/nf33/public/data/ILAMB/ILAMB_RESULT
```

Running ILAMB on <i>Gadi</i> is supported by ACCESS-NRI with further information on <a href="https://access-hive.org.au/model_evaluation/model_evaluation_on_gadi/model_evaluation_on_gadi_ilamb/" target="_blank">this ACCESS-Hive page</a> as well as <a href="https://ilamb-workflow.readthedocs.io/en/latest/" target="_blank"><i>Gadi</i>-specific documentation</a> to supplement the <a href="https://www.ilamb.org" target="_blank">official ILAMB documentation</a>.

## 4. Model Evaluation with ESMValTool

This exercise will introduce you to <a href="https://www.esmvaltool.org/" target="_blank">ESMValTool</a>, a tool to evaluate Earth System Models (ESMs) against observations like those available through the <a href="https://esgf.llnl.gov/index.html" target="_blank">Earth System Grid Federation (ESGF)</a>.

The training material includes
- [a jupyter notebook introduction to ESMValTool](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/esmvaltool/Introduction_to_ESMValTool.ipynb) and
- [an exercise for ESMValTool on <i>Gadi</i>](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/esmvaltool/ESMValTool_training_VDI.md) that will walk you through the evaluation of models with a selected evaluation code recipe.

To run this exercise, you need to be a member of the following NCI projects:
```
nf33, xp65, al33, rr3, r87
```

Running ESMValTool on <i>Gadi</i> is supported by ACCESS-NRI with further information on <a href="https://access-hive.org.au/model_evaluation/model_evaluation_on_gadi/model_evaluation_on_gadi_esmvaltool/" target="_blank">this ACCESS-Hive page</a> to supplement the <a href="https://docs.esmvaltool.org/en/latest/" target="_blank">official ESMValTool documentation</a>.
