# :paw_prints:FelineOS Kernel
Welcome to the official GitHub repository for FelineOS, a custom 64-bit operating system kernel designed for educational and development purposes. Explore the intricacies of OS development by contributing to or building FelineOS.
## :wrench:Requirements
Before you begin, ensure you have the following tools set up and ready:

+ **Text Editor:** Visual Studio Code or any preferred editor.

+ **Docker:** Required for setting up the build environment.

+ **QEMU:** Used for emulating the operating system. Ensure QEMU is added to your path. 

## :rocket:Setup Instructions

### 	:building_construction:Build Environment

First, create the Docker image for the build environment with the following command:


```
docker build -t felineos-buildenv buildenv
```
###  📦Entering the Build Environment

Use one of the following commands based on your operating system to enter the build environment:

+ #### Linux/MacOS:
```
docker run --rm -it -v "$(pwd)":/root/env felineos-buildenv
```
+ #### Windows (CMD):
```
docker run --rm -it -v "%cd%":/root/env felineos-buildenv
```

## :hammer_and_pick:Build Command

Compile FelineOS for x86_64 architecture (future support for other architectures is planned):

```
make build-x86_64
```
Ensure QEMU is not running when you execute this command to avoid conflicts.

## 🚪Exiting the Build Environment

To leave the Docker build environment, simply type:

```
exit
```
## 🖥Emulation
Run your FelineOS build using QEMU with the following command:

+ #### Windows

```
qemu-system-x86_64 -cdrom dist/x86_64/kernel.iso -L "C:\Program Files\qemu"
```
+ #### Linux

```
qemu-system-x86_64 -cdrom dist/x86_64/kernel.iso -L /usr/share/qemu/
```

## 🧹Cleanup

To remove the Docker build environment image:

```
docker rmi felineos-buildenv -f

```




**P.S.:** If you find any expert coding in here, please let me know. It means I accidentally copied from the wrong tutorial. :nerd_face:

