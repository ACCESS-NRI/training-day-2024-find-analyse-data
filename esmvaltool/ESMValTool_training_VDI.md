# ACCESS-NRI ESMValTool Introduction

## Starts VDI Session on ARE

Please refer to the [ARE Setup Guide]() provided for the training.

## Clone the NRI-Workshop2023 GitHub Repository

```bash
cd /scratch/nf33/$USER
git clone https://github.com/ACCESS-NRI/NRI-Workshop2023-MED.git
```

## ESMValTool command line tool

### Step 0: Move to the `esmvaltool` training directory

```bash
cd /scratch/nf33/$USER/NRI-Workshop20230MED/esmvaltool
```

### Step 1: Check the ESMValTool environment by accessing the help for ESMValTool

```bash
module use /g/data/xp65/public/modules
module load conda/access-med

esmvaltool --help
```

### Step 2: The configuration file

We run a text editor called `nano` to have a look inside the configuration file and then modify it if needed:

```bash
nano config-user-on-gadi-v2.9.yml
```

This file contains the information for:

- Output settings
- Destination directory
- Auxiliary data directory
- Number of tasks that can be run in parallel
- Rootpath to input data
- Directory structure for the data from different projects

**KEY POINTS**

- The `config-user-on-gadi-v2.9.yml` tells ESMValTool where to find input data.
- `output_dir` defines the destination directory.
- `rootpath` defines the root path of the data.
- `drs` defines the directory structure of the data.

#### Output settings

The configuration file starts with output settings that inform ESMValTool about your preference for output. You can turn on or off the setting by true or false values. Most of these settings are fairly self-explanatory.

#### Destination directory

The destination directory is the rootpath where ESMValTool will store its output folders containing e.g. figures, data, logs, etc. With every run, ESMValTool automatically generates a new output folder determined by recipe name, and date and time using the format: YYYYMMDD_HHMMSS.

```yaml
# Destination directory where all output will be written
# Includes log files and performance stats.
output_dir: esmvaltool_output
```

#### Rootpath to input data

ESMValTool uses several categories (in ESMValTool, this is referred to as projects) for input data based on their source. The current categories in the configuration file are mentioned below. For example, CMIP is used for a dataset from the Climate Model Intercomparison Project whereas OBS may be used for an observational dataset. More information about the projects used in ESMValTool is available in the documentation. When using ESMValTool on your own machine, you can create a directory to download climate model data or observation data sets and let the tool use data from there. It is also possible to ask ESMValTool to download climate model data as needed. This can be done by specifying a download directory and by setting the option to download data as shown below.

#### Directory for storing downloaded climate data

```yaml
# Directory for storing downloaded climate data
download_dir: esmvaltool_climate_data
search_esgf: never
```

If you are working offline or do not want to download the data then set the option above to never. If you want to download data only when the necessary files are missing at the usual location, you can set the option to when_missing.

The rootpath specifies the directories where ESMValTool will look for input data. For each category, you can define either one path or several paths as a list. For example:

```yaml
# Rootpaths to the data from different projects
# This default setting will work if files have been downloaded by the
# ESMValTool via ``offline=False``. Lists are also possible. For site-specific
# entries and more examples, see below. Comment out these when using a
# site-specific path.
rootpath:
  default: esmvaltool_climate_data
  CMIP5: [/g/data/r87/DRSv3/CMIP5, /g/data/al33/replicas/CMIP5/combined, /g/data/rr3/publications/CMIP5/output1]
  native6: /g/data/nf33/public/data/ESMValTool/obsdata
```
#### Directory structure for the data from different projects

Input data can be from various models, observations and reanalysis data that adhere to the CF/CMOR standard. The drs setting describes the file structure.

The drs setting describes the file structure for several projects (e.g. CMIP6, CMIP5, obs4mips, OBS6, OBS) on several key machines (e.g. BADC, CP4CDS, DKRZ, ETHZ, SMHI, BSC, NCI). For more information about drs, you can visit the ESMValTool documentation on Data Reference Syntax (DRS).

```yaml
# Directory structure for input data --- [default]/ESGF/BADC/DKRZ/ETHZ/etc.
# This default setting will work if files have been downloaded by the
# ESMValTool via ``offline=False``. See ``config-developer.yml`` for
# definitions. Comment out/replace as per needed.
drs:
  CMIP5: BADC
```

## Step 3: Run a recipe inside a PBS Job

To see all the recipes that are shipped with ESMValTool, type

```bash
esmvaltool recipes list
```

Open the `launch_recipe_climwip_test_basic.pbs` file:

```bash
#!/bin/bash -l 

# For help with PBS directives on Gadi, go to https://opus.nci.org.au/display/Help/PBS+Directives+Explained
#PBS -S /bin/bash
#PBS -P nf33
#PBS -l storage=gdata/rr3+gdata/xp65+gdata/al33+gdata/nf33+scratch/nf33
#PBS -N recipe_climwip_test_basic
#PBS -l wd
#PBS -q normal
#PBS -l walltime=01:00:00
#PBS -l mem=64GB
#PBS -l ncpus=10

module use /g/data/xp65/public/modules
module load conda/access-med

esmvaltool run --config_file config-user-on-gadi-v2.9.yml recipe_climwip_test_basic.yml
```

Submit the job to the queue system:

```bash
qsub launch_recipe_climwip_test_basic.pbs
```

## Step 4: Investigating the log messages

You can open the log message and check a few things:

After the banner and general information, the output starts with some important locations.

- Did ESMValTool use the right config file?
- What is the path to the example recipe?
- What is the main output folder generated by ESMValTool?
- Can you guess what the different output directories are for?
- ESMValTool creates two log files. What is the difference?

## Step 5: Visualise outputs

Open a terminal (top left of the VDI screen) and navigate to the esmvaltool result directory, and use the commmand below to start a local  HTTP server.

```bash
python3 -m http.server
```

You can then start Firefox in the VDI screen and access the following address: localhost address:

```
http://0.0.0.0:8000/
```







