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

- *3.2* **Compute Size**: Select `Large (7 cpus, 32G mem)` from the dropdown menu.

<p align="center"><img src="../assets/ARE_setup_guide/setup_image4.png" alt="drawing" width="50%"/></p>

- *3.3* **Project**: Please enter `nf33`. This will allocate SU usage to the workshop project.

<p align="center"><img src="../assets/ARE_setup_guide/setup_image5.png" alt="drawing" width="50%"/></p>

- *3.4* **Storage**: This is the list of `/g/data/` project data storage locations required to complete the workshop tutorials. In ARE, storage locations need to be explicitly defined to access these data from within a JupyterLab instance. Please enter the following string listing the projects mentioned in **Step 0** above: `scratch/nf33+gdata/nf33+gdata/xp65+gdata/fs38+gdata/hh5+gdata/oi10`.

<p align="center"><img src="../assets/ARE_setup_guide/setup_image6.png" alt="drawing" width="50%"/></p>

- *3.5* Click `Advanced options ...`

<p align="center"><img src="../assets/ILAMB/pbsflag.png" alt="drawing" width="49%"/></p>


## Step 4

Once the VDI instance has started (this usually takes around 30 seconds) and this status window should update and look something like the following, reporting that the instance has started and the time remaining. More detailed information on the instance can be accessed by clicking the Session ID link.

 ![running](../assets/ILAMB/running.png)

All that remains to get started is to click `Launch VDI Desktop`.


## Step 5
Start a terminal in the VDI session.

![](../assets/ILAMB/vdi_desktop.png)

Then open a terminal, change the directory to your directory in this training section

```
cd /scratch/nf33/$USER
```

## Step 6
In this directory, we need you to clone the whole repo from GitHub with the command below (if you already have this repo in your directory, you can jump to STEP 7):

```
git clone https://github.com/ACCESS-NRI/workshop-training-2023.git
```

![](../assets/ILAMB/gitclone.png)

Then you are all set to start the exercises.

## Step 7

```
cd ./workshop-training-2023/ilamb
```
Go to the `ilamb` directory. You will see everything we need to run ILAMB on NCI. We have got everything set up so you don't need to organise anything, just use the command below to trigger ILAMB.

```
qsub run_ilamb.pbs
```

![](../assets/ILAMB/runilamb.png)

## Step 8

After the process terminates, you can find details about the ILAMB running process in the output log file created by PBS.

![](../assets/ILAMB/confront.png)
![](../assets/ILAMB/post.png)


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

![](../assets/ILAMB/ilamb_result.png)

You can browse the output by clicking on the links:

![](../assets/ILAMB/ilamb_result1.png)
![](../assets/ILAMB/ilamb_result2.png)

# End of Tutorial

You can find more details in [ilamb_tutorial](https://www.ilamb.org/doc/tutorial.html) and ACCESS-NRI tutorial about [how to use ilamb on NCI](https://ilamb-workflow.readthedocs.io/en/latest/) 
