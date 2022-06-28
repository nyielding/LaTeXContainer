FROM texlive/texlive:latest

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
    sudo \
    openssh-client \
    git \
&& rm -rf /var/lib/apt/lists/* \
&& apt-get clean

WORKDIR /

ARG NEW_USER=vscode
ARG NEW_UID=1000
ARG NEW_GID=1000
ARG NEW_GROUP=vscode

RUN addgroup --gid $NEW_GID $NEW_GROUP \
    && useradd -m -l --uid $NEW_UID --gid $NEW_GID $NEW_USER \
    && usermod -aG sudo ${NEW_USER} \
    && echo "${NEW_USER} ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

WORKDIR /workspace