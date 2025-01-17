Before we start we are going to need to install our python dependencies. This will allow us to have our development environment and runtimes setup for the everything we currently need to get started

## Use APT and pipx to install packages
1. Login to the SSH Console of your running VM
	1. Click the SSH button on the cloud console
	2. Allow to share your SSH keys
2. Update and Upgrade APT packages.
```
sudo apt update && sudo apt upgrade -y
```
3. Install `pipx` package manager.
```
sudo apt install -y pipx
pipx ensurepath
```
4. Install `uv`project manager.
```
pipx install uv
```
5. Reload your PATH in order to activate `uv` usage (located in `~/.bashrc`)
```
source ~/.bashrc
```