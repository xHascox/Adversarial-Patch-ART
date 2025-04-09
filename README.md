# Adversarial Patch ART
 
Based on https://github.com/Trusted-AI/adversarial-robustness-toolbox

pip install -e /path/to/locations/repo



cmd:

nvidia-smi --loop=5




## Dataset:

There are 3 scenarios involving pedestrians:
* ParkingCrossingPedestrian
* PedestrianCrossing
* VehicleTurningRoutePedestrian




### Script: 

https://github.com/autonomousvision/carla_garage/blob/leaderboard_2/tools/download_data.sh

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
for scenario in Accident AccidentTwoWays BlockedIntersection ConstructionObstacle ConstructionObstacleTwoWays ControlLoss CrossingBicycleFlow DynamicObjectCrossing EnterActorFlow EnterActorFlowV2 HardBreakRoute HazardAtSideLane HazardAtSideLaneTwoWays HighwayCutIn HighwayExit InterurbanActorFlow InterurbanAdvancedActorFlow InvadingTurn MergerIntoSlowTraffic MergerIntoSlowTrafficV2 NonSignalizedJunctionLeftTurn NonSignalizedJunctionRightTurn noScenarios OppositeVehicleRunningRedLight OppositeVehicleTakingPriority ParkedObstacle ParkedObstacleTwoWays ParkingCrossingPedestrian ParkingCutIn ParkingExit PedestrianCrossing PriorityAtJunction SignalizedJunctionLeftTurn SignalizedJunctionRightTurn StaticCutIn VehicleOpensDoorTwoWays VehicleTurningRoute VehicleTurningRoutePedestrian YieldToEmergencyVehicle
do
  down_load_unzip "${scenario}" &
done
```

Just the relevant scenarios:

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

Like this:

```
wget https://s3.eu-central-1.amazonaws.com/avg-projects-2/garage_2/dataset/ParkingCrossingPedestrian.tar -OutFile ParkingCrossingPedestrian
```

# asdasd 

