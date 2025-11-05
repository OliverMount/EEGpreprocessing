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

3. Run the preporcessing.m 

4. It would generate the folder called `preprocess` that contains the final and intermediate preprocessed files.

---

### Epoching

1. After preprocessing, the epoching based on the experimental trial length is done using scripts/epoching/Epoching.m file. 

2. Set the epoch_duration for example  ([-0.2 1.2] s) and baseline correction durations (for exmaple  [-200,-10] ms) in the Epoching.m as well the path for the preprocessed data and the toolboxes.

3. Run the Epoching.m. 

4. It would generate condition wise mat files of epoched data for each condition. The conditions for your experiment can be set as in  cond_name.m









