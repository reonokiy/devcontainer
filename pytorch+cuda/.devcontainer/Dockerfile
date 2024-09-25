
FROM pytorch/pytorch:1.9.1-cuda11.1-cudnn8-runtime

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=${USER_UID}

RUN apt-get update && apt-get install -y \
    git \
    curl \
    wget \
    sudo

RUN groupadd --gid ${USER_GID} ${USERNAME} \
    && useradd --uid ${USER_UID} --gid ${USER_GID} -m ${USERNAME} \
    && echo ${USERNAME} ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/${USERNAME} \
    && chmod 0440 /etc/sudoers.d/${USERNAME} \
    && usermod --shell /bin/bash ${USERNAME}

USER ${USERNAME}

RUN conda init bash

CMD ["/bin/bash"]
