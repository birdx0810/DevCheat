# CUDA and cuDNN Installation CheatSheet
Reference: [Link](https://www.tensorflow.org/install/gpu)

## Remove NVIDIA
```
sudo apt clean; sudo apt update; sudo apt purge cuda; sudo apt purge nvidia-*
```

## Add NVIDIA package repositories
```
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/cuda-repo-ubuntu1804_10.1.243-1_amd64.deb
sudo apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/7fa2af80.pub
sudo dpkg -i cuda-repo-ubuntu1804_10.1.243-1_amd64.deb
sudo apt-get update
wget http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1804/x86_64/nvidia-machine-learning-repo-ubuntu1804_1.0.0-1_amd64.deb
sudo apt install ./nvidia-machine-learning-repo-ubuntu1804_1.0.0-1_amd64.deb
sudo apt-get update
```

## Install NVIDIA driver
```
sudo apt-get install --no-install-recommends nvidia-driver-450
# Reboot. Check that GPUs are visible using the command: nvidia-smi
```

## Install development and runtime libraries (~4GB)
```
sudo apt-get install --no-install-recommends \
    cuda-10-0 \
    libcudnn7=7.6.2.24-1+cuda10.0  \
    libcudnn7-dev=7.6.2.24-1+cuda10.0
```

## Install TensorRT. Requires that libcudnn7 is installed above.
```
sudo apt-get install -y --no-install-recommends libnvinfer5=5.1.5-1+cuda10.0 \
    libnvinfer-dev=5.1.5-1+cuda10.0
```

## Uninstall 
```
sudo apt-get --purge remove "*cublas*" "cuda*"
rm /usr/local/cuda-10.1/targets/x86_64-linux/include/thrust/system/cuda
sudo apt-get remove nvidia-cuda-toolkit
sudo apt-get remove --auto-remove nvidia-cuda-toolkit
sudo apt-get purge --auto-remove nvidia-cuda-toolkit

nvidia-installer --uninstall
sudo apt remove nvidia-*
sudo apt-get -y install cuda cuda-10-1 cuda-toolkit-10-1
```

<!--
## Install NVIDIA Graphics Drivers

sudo apt-get install ubuntu-drivers-common

sudo ubuntu-drivers autoinstall

## Install CUDA

sudo apt-get install cuda

## Install cuDNN

wget https://developer.nvidia.com/compute/machine-learning/cudnn/secure/7.6.5.32/Production/10.2_20191118/cudnn-10.2-linux-x64-v7.6.5.32.tgz

tar -xzvf cudnn-10.2-linux-x64-v7.6.5.32.tgz
-->
