# EEG preprocessing

### Preprocessing of ElectroEncephaloGraphy (EEG) signals

The preprocessing of EEG signals is adapted in my manuscript follows the brainX eeglab's principle. I have modified their code to suit to my experimental paradigm 


In order to preprocess the *.mff file for each participant, please follow the following folder structure

1. Place all raw data in the `raw folder` with each participant raw data organized as folder with the raw folder.  The `raw` folder is the one preprocessing scripts targets to sequentially preprocess individual participant.  

```
raw 
├── sub1_20221124
├── sub2_20221226
├── ...
├── sub100_20220825 
```
 
```
cd sub1_20221124
```

Each participant folder contains *.mff files

```
sub1_20221124 
├── sub1_20221124_091749.mff 
├── sub2_20221124_094641.mff 
├── sub3_20221124_100558.mff 


2. 
