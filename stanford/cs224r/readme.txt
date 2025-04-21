$ cat /etc/lsb-release
    DISTRIB_ID=Ubuntu
    DISTRIB_RELEASE=24.04
    DISTRIB_CODENAME=noble
    DISTRIB_DESCRIPTION="Ubuntu 24.04.2 LTS"


Step 0 – Prerequsities
    sudo apt install -y make build-essential git

Step 1 – Download and install miniconda for PythonClient
    mkdir -p ~/miniconda3
    wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
    bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
    rm ~/miniconda3/miniconda.sh

    source ~/miniconda3/bin/activate

    # initialize conda on all available shells 
    conda init --all

Step 1 - Install cuda
    wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2404/x86_64/cuda-keyring_1.1-1_all.deb
    sudo apt install ./cuda-keyring_1.1-1_all.deb
    sudo apt update
    sudo apt install cuda-toolkit
    $ which nvcc
    nvcc --version


Step 3 – Install required packages for CS224R
    cd ~/robotics/stanford/cs224r
    conda env create -f env_224r.yml
    conda activate cs224r
    pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
        Installing collected packages: triton, mpmath, typing-extensions, sympy, setuptools, pillow, nvidia-nvtx-cu11, nvidia-nccl-cu11, nvidia-cusparse-cu11, nvidia-curand-cu11, nvidia-cufft-cu11, nvidia-cuda-runtime-cu11, nvidia-cuda-nvrtc-cu11, nvidia-cuda-cupti-cu11, nvidia-cublas-cu11, numpy, networkx, MarkupSafe, fsspec, filelock, nvidia-cusolver-cu11, nvidia-cudnn-cu11, jinja2, torch, torchvision, torchaudio
        Successfully installed MarkupSafe-3.0.2 filelock-3.13.1 fsspec-2024.6.1 jinja2-3.1.4 mpmath-1.3.0 networkx-3.3 numpy-2.1.2 nvidia-cublas-cu11-11.11.3.6 nvidia-cuda-cupti-cu11-11.8.87 nvidia-cuda-nvrtc-cu11-11.8.89 nvidia-cuda-runtime-cu11-11.8.89 nvidia-cudnn-cu11-9.1.0.70 nvidia-cufft-cu11-10.9.0.58 nvidia-curand-cu11-10.3.0.86 nvidia-cusolver-cu11-11.4.1.48 nvidia-cusparse-cu11-11.7.5.86 nvidia-nccl-cu11-2.21.5 nvidia-nvtx-cu11-11.8.86 pillow-11.0.0 setuptools-70.2.0 sympy-1.13.1 torch-2.6.0+cu118 torchaudio-2.6.0+cu118 torchvision-0.21.0+cu118 triton-3.2.0 typing-extensions-4.12.2
    pip3 install ipycanvas


