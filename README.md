# EEG preprocessing

### Preprocessing of ElectroEncephaloGraphy (EEG) signals

This repository provides scripts and instructions for **preprocessing** and **epoching** ElectroEncephaloGraphy (EEG) data. The preprocessing pipeline is adapted from the brainX EEGLAB principles, with modifications to accommodate a specific experimental paradigm.

### 📂 Folder Structure

Before running the scripts, organize your data as follows: 
 

```
project_root/
├── raw/
│   ├── sub1_20221124/
│   │   ├── sub1_20221124_091749.mff
│   │   ├── sub1_20221124_094641.mff
│   │   └── sub1_20221124_100558.mff
│   ├── sub2_20221226/
│   ├── ...
│   └── sub100_20220825/
└── scripts/
    ├── preprocessing/
    │   └── preprocessing.m
    └── epoching/
        └── Epoching.m

```

Each participant folder within `raw/` should contain their respective .mff files.

### ⚙️ Preprocessing
 
#### Steps

1. Set paths and options in `scripts/preprocessing/preprocessing.m`

	* Define paths for:
		- Raw data
		- EEGLAB and other required toolboxes
	
	* Specify whether `robust detrending` and `high-pass filtering` should be applied.

2. Run preprocessing:

```{matlab}

run('scripts/preprocessing/preprocessing.m')

```

4. After successful preprocessing, a new folder named `preprocess/` will be created containing:

	* Intermediate preprocessing results

	* Final preprocessed EEG datasets

---

### ⏱️ Epoching
After preprocessing, epoch the data according to your experimental conditions.

### Steps

1. Edit settings in `scripts/epoching/Epoching.m`

	* Set the **desired epoch duration**, e.g.:
	```
	epoch_duration = [-0.2 1.2];  % in seconds 
	```
	* Define the **baseline correction window**, e.g.:
	```
	baseline_window = [-200 -10];  % in milliseconds 
	```
	* Adjust paths for:
		- Preprocessed data
		- EEGLAB and toolbox directories
	
 
2. Run epoching:

	```
	run('scripts/epoching/Epoching.m') 
	```
 

3. The script will generate condition-wise .mat files for each participant, stored in an output folder. Conditions are defined in `scripts/epoching/cond_name.m`


---

🧠 Notes

* Ensure that the sampling rate, channel layout, and event markers in .mff files are consistent across participants.

* The preprocessing script processes subjects sequentially from the raw/ directory.

* Modify parameters in the scripts to fit your own experimental design and analysis pipeline.

---

📬 Contact

For questions or adaptation guidance, please contact the repository maintainer or refer to the comments within each MATLAB script.

--- 
