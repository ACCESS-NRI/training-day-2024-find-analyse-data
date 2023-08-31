# ACCESS-NRI Training Day 4 September 2023

This repository includes the material for the <a href="https://www.access-nri.org.au" target="_black">ACCESS-NRI</a> <a href="https://www.access-nri.org.au/event/access-training-day-2023/" target="_black">Training Day</a> on 4 September 2023.  
You can find a general overview of the ACCESS-NRI documentation on the <a href="https://access-hive.org.au" target="_blank">ACCESS-Hive</a>.  

This reopository is structured according to the <a href="https://www.access-nri.org.au/access-training-day-program/" target="_blank">Training Day program</a>:

1. [Launching ARE (Australian Research Environment)](#1-launching-are-australian-research-environment)  
2. [Running ACCESS models and Rose/cylc in ARE](#2-running-access-and-rosecylc-in-are)  
3. [Finding and Loading Model Data with Intake](#3-finding-and-loading-model-data-with-intake)  
4. [Model Evaluation with ILAMB (International Land Model Benchmarking)](#4-model-evaluation-with-ilamb-international-land-model-benchmarking)
5. [Model Evaluation with ESMValTool](#5-model-evaluation-with-esmvaltool)

We value your feedback on this training, in-person or via the <a href="https://forum.access-hive.org.au/" target="_blank">ACCESS-Hive Forum</a>, as it will help us to provide better training and documentation for the ACCESS community on our documentation portal, <a href="https://access-hive.org.au" target="_blank">ACCESS-Hive</a>.

## 1. Launching ARE (Australian Research Environment)  

This part of the training will explain how to use the ARE (https://are.nci.org.au) to launch interactive Jupyter notebooks and desktop interfaces.

The [training material for this exercise](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/ARE_setup_guide.md) includes the following content:  

- `ssh` onto Gadi with a terminal of your choice or <i>Gadi</i> Terminal in ARE 
- Launching JupyterLab Notebook in ARE  
- Launching VDI (Virtual Desktop Interface) in ARE

## 2. Running ACCESS and Rose/cylc in ARE  

This exercise and its [training material](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/access_rose_cylc/rose_cylc_example.md) will walk you through the setup of an [ACCESS Coupled Model 2 (ACCESS-CM2)](https://access-hive.org.au/models/configurations/access-cm/) model run.

## 3. Finding and Loading Model Data with Intake

This exercise will introduce you to the ACCESS-NRI Intake Catalogue, a tool to provide a way for Python users to discover and load data across a broad range of climate data products available on Gadi.

To run this exercise, you need to be member of the following NCI projects:
```
nf33, dk92, fs38, p73, xp65, hh5 (optional)
```

The exercises are split in two parts to be run via an ARE JupyterLab session:

1. [Jupyter notebook exercise part 1](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/intake/Intake_tutorial_p1.ipynb) to introduce the ACCESS-NRI Intake catalog a show you how to use it to find and load model data for analysis.

2. [Jupyter notebook exercise part 2](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/intake/Intake_tutorial_p2.ipynb) to demonstrate how users can build Intake-ESM datastores for their ACCESS model runs using the access-nri-intake Python package.

The ACCESS-NRI Intake Catalogue is currated by ACCESS-NRI with further information on its <a href="https://access-nri-intake-catalog.readthedocs.io/en/latest/index.html" target="_blank">documentation website</a> and <a href="https://access-hive.org.au/model_evaluation/model_evaluation_model_catalogs" target="_blank">this ACCESS-Hive page</a>.

## 4. Model Evaluation with ILAMB (International Land Model Benchmarking)

This exercise and its [training material](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/ilamb/ILAMB_training.md) will walk you the evaluation of models and confrontation with osbervational data with ILAMB.

To run this exercise, you need to be member of the following NCI projects:
```
nf33, xp65, hh5, ct11, oi10, fs38 
```

You can find the expected results of this exercise in this <i>Gadi</i> directory:
```
/g/data/nf33/public/data/ILAMB/ILAMB_RESULT
```

Running ILAMB on <i>Gadi</i> is supported by ACCESS-NRI with further information on <a href="https://access-hive.org.au/model_evaluation/model_evaluation_on_gadi/model_evaluation_on_gadi_ilamb/" target="_blank">this ACCESS-Hive page</a> as well as <a href="https://ilamb-workflow.readthedocs.io/en/latest/" target="_blank"><i>Gadi</i>-specific documentation</a> to supplement the <a href="https://www.ilamb.org" target="_blank">official ILAMB documentation</a>.

## 5. Model Evaluation with ESMValTool

This exercise will introduce you to <a href="https://www.esmvaltool.org/" target="_blank">ESMValTool</a>, a tool to evaluate Earth System Models (ESMs) against observations like those available through the <a href="https://esgf.llnl.gov/index.html" target="_blank">Earth System Grid Federation (ESGF)</a>.

The training material includes
- [a jupyter notebook introduction to ESMValTool](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/esmvaltool/Introduction_to_ESMValTool.ipynb) and
- [a guide for ESMValTool on <i>Gadi</i>](https://github.com/ACCESS-NRI/workshop-training-2023/blob/main/esmvaltool/ESMValTool_training_VDI.md) that will walk you through the evaluation of models with a selected evaluation code recipe.

To run this exercise, you need to be member of the following NCI projects:
```
nf33, xp65, al33, rr3, r87
```


Running ESMValTool on <i>Gadi</i> is supported by ACCESS-NRI with further information on <a href="https://access-hive.org.au/model_evaluation/model_evaluation_on_gadi/model_evaluation_on_gadi_esmvaltool/" target="_blank">this ACCESS-Hive page</a> to supplement the <a href="https://docs.esmvaltool.org/en/latest/" target="_blank">official ESMValTool documentation</a>.