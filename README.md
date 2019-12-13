Docker for pytorch_gpu
------------
- Ubuntu==16.04
- CUDA==10.1
- CUDNN==7
- minconda
- python==3.6(default environment)

# Install nvidia-docker

```bash
# Add the package repositories
$ distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
$ curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
$ curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list

$ sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
$ sudo systemctl restart docker
```

## Verify installation
```bash
docker run --runtime=nvidia --rm nvidia/cuda nvidia-smi
```

# Build from docker file

```bash
docker build -t <username>/<repo-name> pytorch_gpu/
```
# Pull from docker hub
```bash
docker pull airleee/pytorch_gpu_dgl
```
# Run docker

```bash
docker run -v $PWD:/home --runtime=nvidia -p 8888:8888 --name py36_gpu -it <username>/<repo-name> bash
```
