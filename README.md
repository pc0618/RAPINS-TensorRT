# RAPINS-TensorRT

Instructions for running the Tensorflow and TensorRT script on ThetaGPU:

**1. Pull the Singularity container**

The singularity container includes TensorRT 7.1.3 and Tensorflow 2.4.1 as well as the other packages necessary to run the script. Newer versions of Tensorflow and TensorRT appear to break the scripts at the moment. Run the following commands to download the Singularity package.

singularity pull tensorrt.sif docker://pc0618/528da3d80843:latest

**2. Clone this repository**

git clone https://github.com/pc0618/RAPINS-TensorRT.git

**3. Run the Singularity Container**

singularity instance start --nv ./tensorrt.sif tensorrt
singularity shell --nv instance://tensorrt

**4. Go to script directory and change directory names in scripts**

cd /AstrophysicalDLSearch/models/AstrophysicalDLSearch/inferences/preds_on_injections

In both script.py (tensorflow script) and script_trt.py (tensorrt script) change model and data paths by replacing /home/pchaturvedi/AstrophysicalDLSearch... with /directory-contaning-github-repo/AstrophysicalDLSearch

**5. Run each script**

python3 script.py for tensorflow script
python3 script_trt.py for tensorrt script
