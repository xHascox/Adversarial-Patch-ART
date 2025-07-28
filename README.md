# Adversarial Patch ART
 
This repository is based on parts of the adversarial-robustness-toolbox (ART): https://github.com/Trusted-AI/adversarial-robustness-toolbox

The repository allows to interactively generate an [Adversarial Patch](https://arxiv.org/pdf/1712.09665) using a white-box attack on [Yolov5](https://github.com/ultralytics/yolov5)

## Installation:

Clone this repo:

`git clone https://github.com/xHascox/Adversarial-Patch-ART.git`

Download our fork of ART: [https://github.com/xHascox/adversarial-robustness-toolbox](https://github.com/xHascox/adversarial-robustness-toolbox)

`git clone https://github.com/xHascox/adversarial-robustness-toolbox.git`

and install it:

`pip install -e /path/to/xHascox/adversarial-robustness-toolbox`

As well as the other requirements:

`pip install -r requirements. txt`

## Usage:

Run the notebook [Adversarial-Patch-ART-Collusion.ipynb](Adversarial-Patch-ART-Collusion.ipynb), which should be self-explanatory.

## Datasets:

### Dataset V1:

Download Dataset V1: [https://storage.googleapis.com/weebit-shared/ParkingCrossingPedestrian.zip](https://storage.googleapis.com/weebit-shared/ParkingCrossingPedestrian.zip)

This includes 3 scenarios involving pedestrians:
* ParkingCrossingPedestrian
* PedestrianCrossing
* VehicleTurningRoutePedestrian

#### Script: 

Or download it from the original source using the script provided in Carla Garage:
[https://github.com/autonomousvision/carla_garage/blob/leaderboard_2/tools/download_data.sh](https://github.com/autonomousvision/carla_garage/blob/leaderboard_2/tools/download_data.sh)

Or just the relevant scenarios:

```
#!/usr/bin/env bash

mkdir data
cd data

down_load_unzip() {
  wget https://s3.eu-central-1.amazonaws.com/avg-projects-2/garage_2/dataset/$1.tar
  tar -xf $1.tar
  rm $1.tar
}

# Download 2024 garage_v1 dataset
for scenario in ParkingCrossingPedestrian PedestrianCrossing VehicleTurningRoutePedestrian
do
  down_load_unzip "${scenario}" &
done
```

On Windows, one can download individual scenarious using wget, but make sure to specify -OutFile as otherwise it crashes. 

Like this: (repeat for all 3 scenarios)

```
wget https://s3.eu-central-1.amazonaws.com/avg-projects-2/garage_2/dataset/ParkingCrossingPedestrian.tar -OutFile ParkingCrossingPedestrian
```

### Dataset V5:


Download Dataset V5: [https://storage.googleapis.com/weebit-shared/dsv5.zip](https://storage.googleapis.com/weebit-shared/dsv5.zip) 

