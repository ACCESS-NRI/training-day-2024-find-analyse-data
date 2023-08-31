# ACCESS-NRI 2023 Workshop ILAMB Tutorial
<p>Guide for the ILAMB ACCESS-NRI workshop exercises.</p>

## Step 0: Pre-workshop
Join the xp65, hh5, ct11, oi10 and fs38 projects  

## Step 1:
Go to the [Australian Research Environment](https://are.nci.org.au/) website and login with your **NCI username and password**. If you don't have an NCI account, you can sign up for one at the [NCI website](https://my.nci.org.au/mancini/login?next=/mancini/).

<p align="center"><img src="../assets/ARE_setup_guide/setup_image1.png" alt="drawing" width="50%"/></p>

## Step 2:
Click on `Virtual Desktop` under *Featured Apps* to configure a new VDI instance. This option is also available under the *All Apps* section at the bottom of the page and the *Interactive Apps* dropdown located in the top menu.

![dashboard](../assets/ILAMB/dashboard.png)

## Step 3:
You will now be presented with the main VDI instance configuration form. Please complete **only** the fields below - leave all other fields blank or to their default values.

- *3.1* **Walltime**: The number of hours the JupyterLab instance will run. `1` hour is sufficient for each of the tutorials.

<p align="center"><img src="../assets/ARE_setup_guide/setup_image3.png" alt="drawing" width="50%"/></p>

- *3.2* **Compute Size**: Select `tiny` from the dropdown menu.

<p align="center"><img src="../assets/ARE_setup_guide/setup_image4.png" alt="drawing" width="50%"/></p>

- *3.3* **Project**: Please enter `nf33`. This will allocate SU usage to the workshop project.

<p align="center"><img src="../assets/ARE_setup_guide/setup_image5.png" alt="drawing" width="50%"/></p>

- *3.4* **Storage**: This is the list of `/g/data/` project data storage locations required to complete the workshop tutorials. In ARE, storage locations need to be explicitly defined to access these data from within a VDI instance. Please enter the following string: `gdata/nf33`.

<p align="center"><img src="../assets/ARE_setup_guide/setup_image6.png" alt="drawing" width="50%"/></p>

- *3.5* Click `Advanced options ...`



- *3.6* **PBS Flags**
The **xp65** conda environment is a containerised environment that requires the `SINGULARITY_OVERLAYIMAGE` environment variable to be defined.
Copy and paste the following: `-v SINGULARITY_OVERLAYIMAGE=/g/data/xp65/public/apps/med_conda/envs/access-med-0.3.sqsh`
in the **PBS Flags** field of the **advanced options** section:

<p align="center"><img src="../assets/ILAMB/pbsflag.png" alt="drawing" width="60%"/></p>

- *3.7* Click `Launch` to start your VDI Instance.

## Step 4

Once the VDI instance has started (this usually takes around 30 seconds) and this status window should update and look something like the following, reporting that the instance has started and the time remaining. More detailed information on the instance can be accessed by clicking the Session ID link.

<p align="center"><img src="../assets/ILAMB/running.png" alt="drawing" width="60%"/></p>

All that remains to get started is to click `Launch VDI Desktop`.


## Step 5
Start a terminal in the VDI session.

<p align="center"><img src="../assets/ILAMB/vdi_desktop.png" alt="drawing" width="60%"/></p>


Then open a terminal, change the directory to your directory in this training section

```
cd /scratch/nf33/$USER
```
If you get the following error: `bash: cd: /scratch/nf33/$: No such file or directory`,you will first need to create the directory with this 
command:
```
mkdir /scratch/nf33/$USER
```
## Step 6
In this directory, we need you to clone the whole repo from GitHub with the command below (if you already have this repo in your directory, you can jump to STEP 7):

```
git clone https://github.com/ACCESS-NRI/workshop-training-2023.git
```

<p align="center"><img src="../assets/ILAMB/gitclone.png" alt="drawing" width="60%"/></p>

Then you are all set to start the exercises.

## Step 7

```
cd ./workshop-training-2023/ilamb
```
Go to the `ilamb` directory. You will see everything we need to run ILAMB on NCI. We have got everything set up so you don't need to organise anything, just use the command below to trigger ILAMB.

```
qsub run_ilamb.pbs
```

<p align="center"><img src="../assets/ILAMB/runilamb.png" alt="drawing" width="60%"/></p>

It will take about 15 mins to finish, use `qstat` to check the status of the processing.
```
qstat
```

## Step 8

After the process terminates, you can find details about the ILAMB running process in the output log file created by PBS.
The file will be named : `run_ilamb.pbs.o########`

<p align="center"><img src="../assets/ILAMB/confront.png" alt="drawing" width="60%"/></p>
<p align="center"><img src="../assets/ILAMB/post.png" alt="drawing" width="60%"/></p>


You should now see an `ilamb_result` directory which contains all the results created by ILAMB.

Let's move into the directory:

```
cd ./ilamb_result/workshop
```

Launch an **http.server** using python:

```
python3 -m http.server
```

You can then start Firefox on the VDI screen and access the following address:
localhost address:

```
http://0.0.0.0:8000/
```

In this training, we use two datasets as an example to show you how to use ILAMB.
The output should look like this:

<p align="center"><img src="../assets/ILAMB/ilamb_result.png" alt="drawing"/></p>

You can browse the output by clicking on the links:

<p align="center"><img src="../assets/ILAMB/ilamb_result1.png" alt="drawing"/></p>
<p align="center"><img src="../assets/ILAMB/ilamb_result2.png" alt="drawing"/></p>

# End of Tutorial

You can find more details in [ilamb_tutorial](https://www.ilamb.org/doc/tutorial.html) and ACCESS-NRI tutorial about [how to use ilamb on NCI](https://ilamb-workflow.readthedocs.io/en/latest/) 
