## prof Jeff Heaton
https://www.youtube.com/watch?v=r7eExQWKzdc&list=PLjy4p-07OYzuy_lHcRW8lPTLPTTOmUpmi
https://github.com/jeffheaton/app_deep_learning/blob/main/t81_558_class_01_1_overview.ipynb
## Miniconda
https://www.tensorflow.org/install/pip#linux
https://github.com/jeffheaton/t81_558_deep_learning/blob/master/install/tensorflow-install-march-2023.ipynb:
```
wget https://raw.githubusercontent.com/jeffheaton/t81_558_deep_learning/master/tools.yml
conda env create -f tools.yml -n tensorflow
```
```
conda activate tensorflow
```
```
conda install -c conda-forge nb_conda
python -m ipykernel install --user --name tensorflow --display-name "Python 3.9 (tensorflow)"
```
## Tensorflow install
https://github.com/jeffheaton/t81_558_deep_learning/blob/master/install/tensorflow-install-march-2023.ipynb
channels:
    - conda-forge
dependencies:
    - cudatoolkit=11.8.0 
    - nvidia-cudnn-cu11==8.6.0.163
    - jupyter
    - scikit-learn
    - scipy
    - pandas
    - pandas-datareader
    - matplotlib
    - pillow
    - tqdm
    - requests
    - h5py
    - pyyaml
    - flask
    - boto3
    - pip
    - pip:y7y
        - tensorflow
        - bayesian-optimization
        - gym
        - kaggle
## Pytorch install
name: torch
channels:
  - pytorch
  - nvidia
dependencies:
    - python=3.9
    - pip>=19.0
    - pytorch 
    - torchvision 
    - torchaudio
    - jupyter
    - scikit-learn
    - scipy
    - pandas
    - pandas-datareader
    - matplotlib
    - pillow
    - tqdm
    - requests
    - h5py
    - pyyaml
    - flask
    - boto3
    - ipykernel
    - pip:
        - bayesian-optimization
        - facenet-pytorch
