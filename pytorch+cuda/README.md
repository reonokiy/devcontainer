# PyTorch + CUDA

- PyTorch shipped with matching CUDA / cuDNN versions from PyTorch's official Docker images.
- Miniconda installed and base environment activated.
- VSCode user extension installed.
- Login with `vscode` user, not root (if your UID is not 1000, you may need to change the UID. [why?](https://www.docker.com/blog/understanding-the-docker-user-instruction/)).

## Usage

Copy the `.devcontainer` folder to your project and open it with VSCode. With Docker installed, VSCode will prompt you to reopen the project in a container. Click on the prompt and wait for the container to build. Once the container is built, you can start using it.

## Customization Guide

### PyTorch, CUDA, and cuDNN Versions
To change the PyTorch, CUDA, or cuDNN versions, modify the `FROM` line in the `Dockerfile` to the desired version.

### Python Version
To specify a different Python version, add the following line to the `Dockerfile`:
```dockerfile
RUN conda install python=3.x
```

### Additional Packages
To install other packages, use `apt-get` or `conda` in the `Dockerfile`. For example:
```dockerfile
RUN apt-get update && apt-get install -y <package-name>
RUN conda install <package-name>
```

## Useful References

- [Add a non-root user to a container @VSCode](https://code.visualstudio.com/remote/advancedcontainers/add-nonroot-user)
- [Docker options @VSCode](https://code.visualstudio.com/remote/advancedcontainers/docker-options)
- [psaboia/devcontainer-nvidia-base: Example of how to set up a NVIDIA DevContainer with GPU Support for TensorFlow/Keras](https://github.com/psaboia/devcontainer-nvidia-base)
- [Python Miniconda Template](https://github.com/devcontainers/images/tree/main/src/miniconda)
- [PyTorch Docker Images](https://hub.docker.com/r/pytorch/pytorch)
- [Rootless Docker](https://docs.docker.com/engine/security/rootless/) and [Issue](https://github.com/microsoft/vscode-remote-release/issues/4646)

