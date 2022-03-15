# Getting Started

Very strange experience on the installation running on `gpu-server1`, what has worked:

- Follow [https://espnet.github.io/espnet/installation.html](https://espnet.github.io/espnet/installation.html)
    - Run with `make CUDA_VERSION=11.1`
- Install GCC: `conda install -c conda-forge gcc`
- Install GXX: `conda install -c conda-forge gxx_linux-64`
- Install Boost: `conda install -c anaconda boost`
- In `espnet/tools` run `installers/install_kenlm.sh` but modify the file to not `make` just yet (comment that out)
    - Modify `espnet/tools/kenlm/CMakeLists.txt` to have near the top of the file: `cmake_policy(SET CMP0057 NEW)` otherwise `cmake` will complain about certain boost operations
    - Now uncomment the `installers/install_kenlm.sh` lines previously commented and it should build!
