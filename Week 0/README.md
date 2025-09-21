# 🖥️ RISC-V SoC Tapeout

This repository documents the open-source VLSI flow used for a RISC-V SoC tapeout.  
It covers the installation and usage of tools such as **Yosys**, **Icarus Verilog**, **GTKWave**, **Magic**, **Ngspice**, and **OpenLANE**.

## 💻 Environment Setup

- **OS:** Ubuntu 20.04+  
- **VM:** Oracle VirtualBox  
- **System Resources:** 6 GB RAM, 50 GB HDD, 4 vCPUs  

---

## ⚙️ System Preparation

Update system and install base packages:

```bash
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install build-essential git wget curl python3 python3-pip python3-venv make bison flex gawk tcl-dev tk-dev libcairo2-dev libglu1-mesa-dev libncurses-dev readline-dev zlib1g-dev libffi-dev -y

```
## Tool Installation

### Yosys

```
git clone https://github.com/YosysHQ/yosys.git
cd yosys
sudo apt install make
sudo apt-get install clang bison flex libreadline-dev gawk tcl-dev libffi-dev git graphviz xdot pkg-config python3 libboost-system-dev libboost-python-dev libboost-filesystem-dev zlib1g-dev -y
git submodule update --init
make config-gcc
make
sudo make install
yosys --version
yosys
```
![WhatsApp Image 2025-09-21 at 17 48 03](https://github.com/user-attachments/assets/c3df39bc-8879-466f-923e-b72d973f7da5)


### Icarus Verilog

```
sudo apt-get update
sudo apt-get install iverilog -y
iverilog -V
```
![WhatsApp Image 2025-09-21 at 17 51 56](https://github.com/user-attachments/assets/2f0f6f0a-dc19-4d69-8cbb-a76b71e03cad)

### GTKWave

```
sudo apt-get update
sudo apt install gtkwave -y
gtkwave --version
```

![WhatsApp Image 2025-09-21 at 17 53 07](https://github.com/user-attachments/assets/3dbf8ea2-0b9c-4b85-ad76-58ed1233e15a)

### Ngspice

```
tar -zxvf ngspice-37.tar.gz
cd ngspice-37
mkdir release
cd release
../configure --with-x --with-readline=yes --disable-debug
make
sudo make install
ngspice --version
```

![WhatsApp Image 2025-09-21 at 18 28 28](https://github.com/user-attachments/assets/dea29796-b874-4f43-80d0-07b1327efff8)

### Magic

```
sudo apt-get install m4 tcsh csh libx11-dev tcl-dev tk-dev libcairo2-dev mesa-common-dev libglu1-mesa-dev libncurses-dev -y
git clone https://github.com/RTimothyEdwards/magic
cd magic
./configure
make
sudo make install
magic --version
```

![WhatsApp Image 2025-09-21 at 18 44 37](https://github.com/user-attachments/assets/be4d0ba9-c061-47f3-9326-2fd0939848aa)

### OpenLANE

```
sudo apt-get update
sudo apt-get upgrade -y
sudo apt install build-essential python3 python3-venv python3-pip make git apt-transport-https ca-certificates curl software-properties-common -y
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io -y
sudo docker run hello-world
sudo groupadd docker
sudo usermod -aG docker $USER
sudo reboot
# After reboot
docker run hello-world
```

![WhatsApp Image 2025-09-21 at 18 52 12](https://github.com/user-attachments/assets/ea2d7600-2a04-4a22-8e93-3e114ff8ffbc)

# Install OpenLANE PDKs and Tools

```
cd $HOME
git clone https://github.com/The-OpenROAD-Project/OpenLane
cd OpenLane
make
make test
```
