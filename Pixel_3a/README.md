# Description for Pixel 3a

For running zTT on Pixel 3a, you need *a client device* (e.g., labtop or desktop) which is connected to Monsoon power monitor for measuring power consumption of Pixel 3a and also you need *a device for zTT agent server*.

**Note that, the client device, the agent server device and Pixel 3a should connected to _same WiFi AP_.**

To connect monsoon power monitor and your Pixel 3a device, you need to detach the battery of Pixel 3a.

## Install dependencies

#### 1. Pixel 3a
Install WiFi-adb application from below link. <br>
https://play.google.com/store/apps/details?id=com.ttxapps.wifiadb&hl=ko&gl=US

#### 2. Client & Agent server device

Clone this repository or download zip file.

Install python dependencies on a client device.

```bash
$ cd Pixel 3a
$ pip install -r requirements.txt
```

## Instruction

Please turn on Monsoon power monitor first.

Then, run *power_on.py* to turn on Pixel 3a.

```bash
$ python power_on.py
```

### 1. Pixel 3a
 1. Start WiFi-adb and **check your IP address**.
    Note that, you need the IP address for connecting Pixel 3a to the client device.
 2. Start an application on Pixel 3a.

### 2. Agent server device
Run *agent.py.*

```bash
$ python agent.py
```

### 3. Client device
Run *client.py.*

#### Usage of client.py
```
usage: client.py [-h] --app {showroom,skype,call} [--exp_time EXP_TIME]
                      --server_ip SERVER_IP [--server_port SERVER_PORT]
                      --target_fps TARGET_FPS --pixel_ip PIXEL_IP

optional arguments:
  -h, --help            show this help message and exit
  --app {showroom,skype,call}   Application name for learning
  --exp_time EXP_TIME           Time steps for learning
  --server_ip SERVER_IP         Agent server IP
  --server_port SERVER_PORT     Agent server port number
  --target_fps TARGET_FPS       Target FPS
  --pixel_ip PIXEL_IP           Pixel device IP for connecting device via adb
```

#### Example
```bash
$ python client.py --app showroom --exp_time 500 --server_ip 192.168.1.24 --target_fps 60 --pixel_ip 192.168.1.35
```


