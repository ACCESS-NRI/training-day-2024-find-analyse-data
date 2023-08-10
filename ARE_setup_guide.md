# ACCESS-NRI Workshop ARE setup guide
<p>Quick-start guide to setting up a JupyterLab session using the Australian Research Environment to run the ACCESS-NRI workshop exercises.</p>

## Step 0:
In order to get the full benefit of the workshop tutorials, access to specific project data on Gadi is required. To help things run as smoothly as possible on the day, please visit the [NCI website](https://my.nci.org.au/mancini/login?next=/mancini/) and join the following projects:
`nf33`, `xp65`, `dk92`, `fs38`, `p73`, `hh5` and `oi10` **prior** to the day of the workshop.

## Step 1:
Go to the [Australian Research Environment](https://are-auth.nci.org.au/) website and login with your **NCI username and password**. If you don't have an NCI account, you can sign up for one at the [NCI website](https://my.nci.org.au/mancini/login?next=/mancini/).

<p style="text-align:center;"><img src="assets/ARE_setup_guide/setup_image1.png" alt="drawing" width="50%"/></p>

## Step 2:
Click on `JupyterLab` under *Featured Apps* to configure a new JupyterLab instance. This option is also available under the *All Apps* section at the bottom of the page and the *Interactive Apps* dropdown located in the top menu.

<p style="text-align:center;"><img src="assets/ARE_setup_guide/setup_image2.png" alt="drawing" width="50%"/></p>

## Step 3:
You will now presented with the main JupyterLab instance configuration form. Please complete **only** the fields below - leave all other fields blank or to their default values.

<p style="text-align:center;"><img src="assets/ARE_setup_guide/setup_image3.png" alt="drawing" width="50%"/></p>

- *3.1* **Walltime**: The number of hours the JupyterLab instance will run. `1` hour is sufficient for each of the tutorials.

<p style="text-align:center;"><img src="assets/ARE_setup_guide/setup_image4.png" alt="drawing" width="50%"/></p>

- *3.2* **Compute Size**: Select `Large (7 cpus, 32G mem)` from the dropdown menu.

<p style="text-align:center;"><img src="assets/ARE_setup_guide/setup_image5.png" alt="drawing" width="50%"/></p>

- *3.3* **Project**: Please enter `nf33`. This will allocate SU usage to the workshop project.

<p style="text-align:center;"><img src="assets/ARE_setup_guide/setup_image6.png" alt="drawing" width="50%"/></p>

- *3.4* **Storage**: This is the list of `/g/data/` project data storage locations required to complete the workshop tutorials. In ARE, storage locations need to be explicitly defined to access these data from within a JupyterLab instance. Please enter the following string listing the projects mentioned in **Step 0** above: `gdata/nf33+gdata/xp65+gdata/dk92+gdata/fs38+gdata/p73+gdata/hh5+gdata/oi10`.

<p style="text-align:center;"><img src="assets/ARE_setup_guide/setup_image7.png" alt="drawing" width="50%"/></p>

- *3.5* Click `Advanced options ...`
<p><b>Optional</b>: You can check the box here to receive an email notification when your JupyterLab instance starts, but as we are only running relatively small instances, they will spin up quickly and this probably isn't necessary.</p>

- *3.6* **Module directories / Modules**: There are two primary `conda` environments that will be used in the tutorials, either `xp65` or `hh5`. Please note, this will not work unless you have both joined the project (Step 0) **and** added it to storage (Step 3.4).<br></br>

<p style="text-align:center;"><img src="assets/ARE_setup_guide/setup_image8.png" alt="drawing" width="50%"/></p>
<p style="text-align:center;"><img src="assets/ARE_setup_guide/setup_image9.png" alt="drawing" width="50%"/></p>

- *3.6.1* If you are instructed to use `hh5`, please enter `/g/data/hh5/public/modules` into the **Module directories** field and `conda/analysis3` into the **Modules** field to use the [hh5 conda environment](https://climate-cms.org/posts/2023-02-27-introducing-new-conda.html).

<p style="text-align:center;"><img src="assets/ARE_setup_guide/setup_image10.png" alt="drawing" width="50%"/></p>
<p style="text-align:center;"><img src="assets/ARE_setup_guide/setup_image11.png" alt="drawing" width="50%"/></p>

- *3.6.2* If you are instructed to use `xp65`, please enter `/g/data/xp65/public/modules` into the **Module directories** field and `conda/med ` into the **Modules** field to use the [ACCESS-NRI MED conda environment](https://github.com/ACCESS-NRI/MED-condaenv).
<br></br>

<p style="text-align:center;"><img src="assets/ARE_setup_guide/setup_image12.png" alt="drawing" width="50%"/></p>

- *3.7* Click `Launch` to start your JupyterLab instance.
