# [Moreh] Test alpha-zero-general on Nvidia-A100 machine
![](https://badgen.net/badge/Nvidia-A100/failed/red)

## Prepare

### Data
- Don't have to prepare data as they will be generated during training

### Code
```bash
git clone https://github.com/suragnair/alpha-zero-general
cd alpha-zero-general
```
### Environment
On Nvidia-A100 machine, NVCC version 11.2.0
```bash
conda create -n alpha-zero-general python=3.8
conda activate swinbert
```
### Run
1. Reproduce the CUDNN_STATUS_EXCECUTION_FAILED error

First, install the CUDA container Toolkit https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html.
Change the directory to alpha-zero-general. 
Then run the below script to create container environment.
```bash
./setup_env.sh
```
If sudo is needed to run docker, run 
```bash
sudo /bin/bash setup_env.sh
```
Finally, run 
```bash
docker exec -ti pytorch_notebook python main.py
```
to reproduce the error.
