# 

## Setup
1. Init submodules
```
git submodule update --init
```
2. Download the **robot simulation platform**, CoppeliaSim. This tutorial is compatible with the version 4.1.0. 
```
wget https://coppeliarobotics.com/files/CoppeliaSim_Edu_V4_1_0_Ubuntu20_04.tar.xz --no-check-certificate
# or download from version  official 
mkdir CoppeliaSim
tar -xvf CoppeliaSim_Edu_V4_1_0_Ubuntu20_04.tar.xz -C ./CoppeliaSim --strip-components 1
rm CoppeliaSim_Edu_V4_1_0_Ubuntu20_04.tar.xz
```
3. Install [**MongoDB**](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/). This tutorial is compatible with the version 5.0.6 () 
```
curl -fsSL https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add -
#echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list
sudo apt update
sudo apt install -y mongodb-org
```

4. You need to install
```
python3.6
python3.6-dev
python3-virtualenv

tmux

gcc
```


5. Add the following to ~/.bashrc or ~/.zshrc: (NOTE: the 'EDIT ME' in the first line)
```
export COPPELIASIM_ROOT=EDIT/ME/PATH/TO/COPPELIASIM/INSTALL/DIR
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$COPPELIASIM_ROOT
export QT_QPA_PLATFORM_PLUGIN_PATH=$COPPELIASIM_ROOT
```
Don't forget restart session.

6. Run training
```
cd catalyst-rl-tutorial
scripts/run-training.sh
```
