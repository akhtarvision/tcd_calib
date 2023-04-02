## Installation

### Requirements:
- PyTorch >= 1.4.0 Installation instructions can be found in https://pytorch.org/get-started/locally/.
- torchvision==0.2.1
- cocoapi
- yacs
- matplotlib
- GCC >= 4.9

### Option 1: Step-by-step installation

```bash
# first, make sure that your conda is setup properly with the right environment
# for that, check that `which conda`, `which pip` and `which python` points to the
# right path. From a clean conda env, this is what you need to do

conda create --name tcd python=3.8
conda activate tcd

# this installs the right pip and dependencies for the fresh python
conda install ipython

# FCOS and coco api dependencies
pip install ninja yacs cython matplotlib tqdm

# follow PyTorch installation in https://pytorch.org/get-started/locally/

conda install pytorch==1.4.0 torchvision==0.2.1 cudatoolkit=10.1 -c pytorch

export INSTALL_DIR=$PWD

# install pycocotools. Please make sure you have installed cython.
cd $INSTALL_DIR
git clone https://github.com/cocodataset/cocoapi.git
cd cocoapi/PythonAPI
python setup.py build_ext install

# install PyTorch Detection
cd $INSTALL_DIR
git clone https://github.com/akhtarvision/tcd_calib.git
cd tcd_calib

# the following will install the lib with
# symbolic links, so that you can modify
# the files if you want and won't need to
# re-build it
python setup.py build develop


unset INSTALL_DIR
