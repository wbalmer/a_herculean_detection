[![DOI](https://zenodo.org/badge/987335798.svg)](https://doi.org/10.5281/zenodo.15483952)

W. Balmer (May 20th, 2025)

This notebook should allow the user to reproduce the data reduction, starlight subtraction, contrast calibration, and source extraction for JWST GO 3337 (DBG & Balmer et al. 2025, ApJL). The notebook itself is citeable as a DOI: 10.5281/zenodo.15483952

To run this notebook, you'll need to create a new conda environment and install stpsf, pyklip, spaceklip, etc and then open this notebook with a ipykernel based in that environment with the correct environment variables.

Download the spaceklip git repo:
```
git clone https://github.com/spacetelescope/spaceKLIP.git
```
Create a new env with the right python version:
```
conda create -n spaceklip_v2p1 python=3.11
conda activate spaceklip_v2p1
```

(optionally, you can create a jupyter kernel, and run this notebook on that kernel explicitly):

```
pip install ipykernel
python -m ipykernel install --user --name=spaceklip_v2p1
```

Cd into the repo, checkout the version of spaceklip that was used for the paper (v2.1), install the requirements, and finally install spaceklip itself.
```
cd spaceKLIP
git checkout 11df3a1
pip install jwst==1.18
pip install -r requirements.txt
pip install -e .
```

In the paper, we used CRDS_VER='12.1.5  ' and the 'jwst_1364.pmap' CRDS context.

Download the stpsf reference files from [here](https://stpsf.readthedocs.io/en/latest/installation.html) and set up the correct environment variables, for example:
```
export STPSF_PATH=$HOME/data/stpsf-data
export WEBBPSF_EXT_PATH='$HOME/data/webbpsf_ext_data/'
export PYSYN_CDBS='$HOME/data/cdbs/'
```
