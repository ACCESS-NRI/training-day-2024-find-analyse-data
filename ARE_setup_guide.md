# ACCESS-NRI Workshop ARE setup guide
<p>Quick-start guide to setting up a JupyterLab session using the Australian Research Environment to run the ACCESS-NRI workshop exercises.</p>

## Step 0: Pre-workshop
- *0.1* In order to get the full benefit of the workshop tutorials, access to specific project data on Gadi is required. To help things run as smoothly as possible on the day, please visit the [NCI website](https://my.nci.org.au/mancini/login?next=/mancini/) and join the following projects:
`nf33`, `xp65`, `dk92`, `fs38`, `rr3`, `al33`, `p73`, `ct11`, `hh5` and `oi10` **prior** to the day of the workshop.

- *0.2* Log into Gadi via command line using your NCI username and password.
  
   ```bash
  ssh <your_gadi_username>@gadi.nci.org.au
  ```

- *0.3* Clone the [workshop-training-2023](https://github.com/ACCESS-NRI/NRI-Workshop2023-MED/tree/main) Github repo to your user directory within `/scratch/nf33` on Gadi. This repo contains the training material needed for the afternoon. Depending on whether or not you've used the `nf33` project before, your user directory may or may not already exist.

  ```bash
  mkdir -p /scratch/nf33/$USER
  cd /scratch/nf33/$USER
  git clone https://github.com/ACCESS-NRI/NRI-Workshop2023-MED.git
  ```

## Step 1:
Go to the [Australian Research Environment](https://are.nci.org.au/) website and login with your **NCI username and password**. If you don't have an NCI account, you can sign up for one at the [NCI website](https://my.nci.org.au/mancini/login?next=/mancini/).

<p align="center"><img src="assets/ARE_setup_guide/setup_image1.png" alt="drawing" width="50%"/></p>

## Step 2:
Click on `JupyterLab` under *Featured Apps* to configure a new JupyterLab instance. This option is also available under the *All Apps* section at the bottom of the page and the *Interactive Apps* dropdown located in the top menu.

<p align="center"><img src="assets/ARE_setup_guide/setup_image2.png" alt="drawing" width="50%"/></p>

## Step 3:
You will now be presented with the main JupyterLab instance configuration form. Please complete **only** the fields below - leave all other fields blank or to their default values.

<p align="center"><img src="assets/ARE_setup_guide/setup_image3.png" alt="drawing" width="50%"/></p>

- *3.1* **Walltime**: The number of hours the JupyterLab instance will run. `1` hour is sufficient for each of the tutorials.

<p align="center"><img src="assets/ARE_setup_guide/setup_image4.png" alt="drawing" width="50%"/></p>

- *3.2* **Compute Size**: Select `Large (7 cpus, 32G mem)` from the dropdown menu.

<p align="center"><img src="assets/ARE_setup_guide/setup_image5.png" alt="drawing" width="50%"/></p>

- *3.3* **Project**: Please enter `nf33`. This will allocate SU usage to the workshop project.

<p align="center"><img src="assets/ARE_setup_guide/setup_image6.png" alt="drawing" width="50%"/></p>

- *3.4* **Storage**: This is the list of `/g/data/` project data storage locations required to complete the workshop tutorials. In ARE, storage locations need to be explicitly defined to access these data from within a JupyterLab instance. Please enter the following string listing the projects mentioned in **Step 0** above: `scratch/nf33+gdata/nf33+gdata/xp65+gdata/dk92+gdata/fs38+gdata/p73+gdata/hh5+gdata/oi10+gdata/rr3+gdata/al33`.

<p align="center"><img src="assets/ARE_setup_guide/setup_image7.png" alt="drawing" width="50%"/></p>

- *3.5* Click `Advanced options ...`
  * Optional: You can check the box here to receive an email notification when your JupyterLab instance starts, but as we are only running relatively small instances, they will spin up quickly and this probably isn't necessary.</p>

<p align="center"><img src="assets/ARE_setup_guide/setup_image8.png" alt="drawing" width="49%"/></p>

- *3.6* **Extra arguments**: By default, the working directory of your JupyterLab instance will be your home directory. Add the extra argument `--notebook-dir=/scratch/nf33/$USER` to set the working directory to your user directory in `/scratch/nf33`.

- *3.7* **Module directories / Modules**: There are two primary `conda` environments that will be used in the tutorials, either `xp65` or `hh5`. Please note, this will not work unless you have both joined the project (Step 0) **and** added it to storage (Step 3.4).<br></br>

<p align="center"><img src="assets/ARE_setup_guide/setup_image9.png" alt="drawing" width="50%"/></p>
<p align="center"><img src="assets/ARE_setup_guide/setup_image10.png" alt="drawing" width="50%"/></p>

- *3.7.1* If you are instructed to use `hh5`, please enter `/g/data/hh5/public/modules` into the **Module directories** field and `conda/analysis3-unstable` into the **Modules** field to use the [hh5 conda environment](https://climate-cms.org/posts/2023-02-27-introducing-new-conda.html).

<p align="center"><img src="assets/ARE_setup_guide/setup_image11.png" alt="drawing" width="50%"/></p>
<p align="center"><img src="assets/ARE_setup_guide/setup_image12.png" alt="drawing" width="50%"/></p>

- *3.7.2* If you are instructed to use `xp65`, please enter `/g/data/xp65/public/modules` into the **Module directories** field and `conda/access-med` into the **Modules** field to use the [ACCESS-NRI MED conda environment](https://github.com/ACCESS-NRI/MED-condaenv).
<br></br>

<p align="center"><img src="assets/ARE_setup_guide/setup_image13.png" alt="drawing" width="50%"/></p>

- *3.8* Click `Launch` to start your JupyterLab instance.

## Step 4:
Once you have clicked `Launch` the browser will redirect to the 'interactive sessions' page where you will see your JupyterLab instance details and current status which will look something like this:

<p align="center"><img src="assets/ARE_setup_guide/setup_image14.png" alt="drawing" width="50%"/></p>

Once the JupyterLab instance has started (this usually takes around 30 seconds) and this status window should update and look something like the following, reporting that the instance has started and the time remaining. More detailed information on the instance can be accessed by clicking the `Session ID` link.

<p align="center"><img src="assets/ARE_setup_guide/setup_image15.png" alt="drawing" width="50%"/></p>

All that remains to get started is to click `Open JupyterLab`. This opens the instance a new browser window. Use the navigation tools in the left-hand panel to navigate to the location of the cloned tutorial files (`/scratch/nf33/$USER`) and open the tutorial notebooks.
