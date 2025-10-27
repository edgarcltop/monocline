<p align="center">
  <h1 align="center">MonoSDF: Exploring Monocular Geometric Cues for Neural Implicit Surface Reconstruction</h1>
</p>

<p align="center">
We demonstrate that state-of-the-art depth and normal cues extracted from monocular images are complementary to reconstruction cues and hence significantly improve the performance of implicit surface reconstruction methods. 
</p>
<br>

# Setup

## Installation
Clone the repository and create an anaconda environment called monosdf using
```
cd monosdf

conda create -y -n monosdf python=3.8
conda activate monosdf

conda install pytorch torchvision cudatoolkit=11.3 -c pytorch
conda install cudatoolkit-dev=11.3 -c conda-forge

pip install -r requirements.txt
```

## DTU
First, download the ground truth DTU point clouds:
```
bash scripts/download_dtu_ground_truth.sh
```
then you can evaluate the quality of extracted meshes (take scan 65 for example):
```
python evaluate_single_scene.py --input_mesh scan65_mesh.ply --scan_id 65 --output_dir dtu_scan65
```

We also provide script for evaluating all DTU scenes:
```
python evaluate.py
```
Evaluation results will be saved to ```evaluation/DTU.csv``` by default, please check the script for more details.

## ScanNet
```
cd scannet_eval
python evaluate.py
```

