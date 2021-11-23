# Neuropixels trajectory explorer
Neuropixels trajectory explorer with the Allen CCF mouse atlas

**NOTE ON UPDATES:** This program will be updated in the (hopefully) near future with better scaling

**NOTE ON SCALING:** The Allen CCF mouse atlas is slightly larger in the DV axis than a real brain (i.e. it is _not_ scaled accurately or isometrically). This GUI incorporates a scaling factor to compensate for this, currently estimated at 92.5% in the DV axis (100% in the AP/ML axes). This is provisional, and will be updated in the future based on CCF/MRI alignment. 

Any issues/bugs/suggestions, please open a github issue by clicking on the 'Issues' tab above and pressing the green 'New issue' button.

## Requirements, setup, starting
- Download the Allen CCF mouse atlas (all files at http://data.cortexlab.net/allenCCF/)

(this is a re-formatted version of the original atlas found here http://download.alleninstitute.org/informatics-archive/current-release/mouse_ccf/annotation/ccf_2017/, which has been processed using https://github.com/cortex-lab/allenCCF/blob/master/setup_utils.m)

### If you have MATLAB
- Download/clone this repository

- Download/clone the NPY-matlab repository: https://github.com/kwikteam/npy-matlab
(this is code to load the formatted CCF atlas)

- Add the folders with the CCF atlas, the NPY-matlab repository, and this repository into the MATLAB path
(File > Set Path > Add with subfolders... > select the downloaded folder (have to do this for each folder separately), then hit 'Save' and 'Close')

- Run the command in MATLAB:
```matlab
neuropixels_trajectory_explorer
```

### If you don't have MATLAB
- Run neuropixels_trajectory_explorer_installer.exe (also installs MATLAB runtime environment)
- The first time the explorer is run, you will be prompted to select the folder where you installed the CCF atlas. Navigate to the folder with the atlas and hit 'ok'.

## Instructions

A video demo of usage (from the UCL Neuropixels 2021 course on a slightly older version) is here: https://www.youtube.com/watch?v=ZtiX0iunUTM

### Overview of interface
![image](https://github.com/petersaj/neuropixels_trajectory_explorer/blob/main/wiki/overview.PNG)
- Left: control panel with directions for moving the probe and buttons to change what is displayed
- Middle: the atlas and probe, the view can be rotated by clicking and dragging
- Right: the brain areas the probe passes through in it's current orientation

![image](https://github.com/petersaj/neuropixels_trajectory_explorer/blob/main/wiki/control_panel.PNG)
- Probe controls: arrow keys (translate), SHIFT+arrow keys (rotate probe by moving bottom), ALT+arrow keys (depth along probe axis), manually enter position
- 3D areas: pick an area (through a comprehensive list, search or hierarchy) to draw in 3D on the atlas
- Toggle visibility: turn on/off visibility ('Slice' switches between displaying anatomy, CCF-parsed regions, or nothing)
- - Other: not currently in regular use


### Experimental use of Neuropixels coordinates
The coordinates of the probe are displayed above the atlas relative to **bregma (anterior/posterior and medial/lateral)** and the **brain surface (depth, axis along the probe)**

The angles of the manipulator are displayed as the **azimuth (polar) relative to the line from tail to nose, where 0 degrees means the probe is coming straight from behind the mouse**, and to the **elevation (pitch) relative to the horizontal, where 90 degrees means the probe is going straight downward**.

![image](https://github.com/petersaj/neuropixels_trajectory_explorer/blob/main/wiki/angles.png)


During the experiment:
- The manipulator angles should be set relative to the midline (azimuth/polar angle) and horizontal (pitch angle)
- The probe should be positioned over bregma and the AP/ML coordinates should be zeroed, then the probe should lightly touch the brain in the desired insertion spot and the probe-axis coordinate should be zeroed
- The probe should be lowered along the probe-axis until it reaches the desired probe-axis coordinate
