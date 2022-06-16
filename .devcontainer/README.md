# Development container

Development container that can be used with VSCode.

It works on Linux, Windows and OSX.

## Requirements

- [VS code](https://code.visualstudio.com/download) installed
- [VS code remote containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) installed
- [Docker](https://www.docker.com/products/docker-desktop) 
    - VSCode can mostly automate installing Docker Desktop and WSL2 on Windows when you first try to open in container
- [Docker Compose](https://docs.docker.com/compose/install/) installed (Docker Desktop on Windows has this already)
- To use Git, ensure your host has the following and that they are accessible by Docker:
    - `~/.ssh` directory
    - `~/.gitconfig` file (can be empty)
    - If the above is confusing, try installing openssh and looking in your home directory (On Windows with "show hidden files" enabled, C:\Users\<your_user> is home

## Setup

1. Open the command palette in Visual Studio Code (F1 or CTRL+SHIFT+P).
2. Select `Remote-Containers: Open Folder in Container...` and choose the project directory.

OR
1. Click the "><" symbol in the lower left corner of VSCode, select `Remote-Containers: Open Folder in Container...`

### ~/.ssh/config permission issues with Git

If you have issues with git push in this vscode container, try changing permissions on the config file (or just delete it if you don't use it for anything else).
Once in the container terminal:
```
chmod 600 /root/.ssh/config
```