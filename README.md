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

This will install the Q-Score bundle in chimera. We still need to add the pre-compiled binary to the bundle by hand. On MacOS, this directory is in `~/Library/'Application Support'/ChimeraX/your_chimerax_version`. The Linux path should be fairly easy to find and the binary is also included in this repo.

So, for ChimeraX version 1.9.x on MacOS for example, we would run:


```bash
cp /path/to/chimerax-qscore/_kmeans.cpython-311-darwin.so ~/Library/'Application Support'/ChimeraX/1.9/lib/python/site-packages/chimerax/
```