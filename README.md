Implementation of the map-model Q-Score algorithm (https://www.nature.com/articles/s41592-020-0731-1) in ChimeraX.

# Installable Q-Sore Bundle

This repo includes the compiled C++ binaries for computing the spherical K-means clustering algorithm, along with all of the necessary files for installation in ChimeraX. This version of the Q-Score bundle exposes the "set attr" function that allows the user to colormap the Q-score for each atom onto the model without needing to go through the old Chimera. I created this fork because I saw that the feature was implemented in the GitHub repo but for some reason isn't included in the bundle available through the ChimeraX toolshed. I couldn't quickly get the C++ file to compile so I just pulled the binaries from the wheels available in the Toolshed and installed with the following two step method. 

## Installation instructions

In a terminal, clone this repo using the following command:

```bash
# clone this repo
$ git clone https://github.com/ray-berkeley/chimerax-qscore.git
```

In ChimeraX, run the following command:

```
devel install /path/to/chimerax-qscore/
```

## Finding binaries for other platforms

Linux or Windows binaries can be found in the [QScore Bundle in the ChimeraX Toolshed](https://cxtoolshed.rbvi.ucsf.edu/apps/chimeraxqscore). Download the bundle for your platform, unzip it, and move the binary to src:

```bash
cd /download/path

unzip ./ChimeraX_QScore-1.1-cp311-cp311-linux_x86_64.whl
cp ChimeraX/qscore/_kmeans.cpython-311-x86_64-linux-gnu.so /path/to/chimerax-qscore/src/
```

Then install like before in the ChimeraX command line:

```
devel install /path/to/chimerax-qscore/
```