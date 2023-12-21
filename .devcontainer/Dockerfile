# 元となるdockerイメージを指定
FROM python:3.10

# wslのデフォルトユーザーでdockerコンテナ内を操作できるように設定
ARG USERNAME=developer
ARG GROUPNAME=localuser
ARG UID=1000
ARG GID=1000
ARG PASSWORD=pass
RUN groupadd -g $GID $GROUPNAME && \
    useradd -m -s /bin/bash -u $UID -g $GID -G sudo $USERNAME && \
    echo $USERNAME:$PASSWORD | chpasswd && \
    echo "$USERNAME   ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
USER $USERNAME