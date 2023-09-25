## Carla Simulator

### [Installation](https://carla.readthedocs.io/en/0.9.14/start_quickstart/)
- Debian CARLA 9.13 Installation on Ubuntu 20.04
  ```
  sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 1AF1527DE64CB8D9
  sudo add-apt-repository "deb [arch=amd64] http://dist.carla.org/carla $(lsb_release -sc) main"
  sudo apt-get update # Update the Debian package index
  sudo apt-get install carla-simulator # Install the latest CARLA version, or update the curren installation
  cd /opt/carla-simulator # Open the folder where CARLA is installed
  ```
- Package Installation
  ```
  cd opt/carla_simulator/
  ./ImportAssets.sh
  ```

### [Add G29 Racing Wheel.ini file](https://github.com/carla-simulator/carla/issues/2575)
- switch to PS3 mode
- create a file with name "wheel_config.ini" in /opt/carla-simulator/PythonAPI/examples/ and paste
  "
  [G29 Racing Wheel]
  steering_wheel = 0
  clutch = 1
  throttle = 2
  brake = 3
  handbrake = 4
  reverse = 5
  "

### Running CARLA
1. run server
  ```
  cd opt/carla_simulator/
  ./CarlaUE4.sh
  ```
2. run client script
  ```
  cd /opt/carla-simulator/PythonAPI/examples/
  python3 manual_control_steeringwheel.py --res 5760x1080
  ```
3. generate traffic (spawn 20 vehicles and 50 walkers)
  ```
  cd /opt/carla-simulator/PythonAPI/examples/
  python3 generate_traffic.py -n 20 -w 50
  ```
