# Example-Apps
Some Example apps with their configuration files which are ready to run on Paradrop.

## Installation
To install any of the apps on a device running Paradrop please do the following:
* Install the pdtools command line tools for Paradrop. 
```
sudo pip install pdtools
```
* From the directory with the config.yaml and Dockerfile for the app run:
```
paradrop install <host-url> <port> config.yaml
```
* Enjoy your app running on Paradrop!
