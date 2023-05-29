# airspy_fft_ws

A daemon to serve an FFT over websocket

## Download

```
git clone --recursive https://github.com/BritishAmateurTelevisionClub/eshail-ghy-wb-fft-airspy.git
```

## Install libairspy dependency

```
sudo apt install libairspy-dev libfftw3-dev
```

## Install airspy host to get serial number

```
wget https://github.com/airspy/airspyone_host/archive/master.zip
unzip master.zip
cd airspyone_host-master
mkdir build
cd build
cmake ../ -DINSTALL_UDEV_RULES=ON
make
sudo make install
sudo ldconfig
```
## Run airspy_info to get serial
Copy value and paste in main.c

```
airspy_lib_version: 1.0.9

Found AirSpy board 1
Board ID Number: 0 (AIRSPY)
Firmware Version: AirSpy NOS v1.0.0-rc10-6-g4008185 2020-05-08
Part ID Number: 0x6906002B 0x00000030
Serial Number: 0x573064DC316F20C1
Supported sample rates:
        10.000000 MSPS
        2.500000 MSPS
Close board 1
```

## Build libwebsockets dependency (no system install)

```
cd libwebsockets/
mkdir build/
cd build/
cmake .. -DLWS_WITH_SSL=OFF
make
```

## Compile

```
make
```

## Install as systemd service

```
./install
```

# Copyright 2019 British Amateur Television Club
