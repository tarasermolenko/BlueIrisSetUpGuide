# BlueIris Set Up Guide (In progress)

## Use Case:
6 1080p/720p cameras at 15-30 FPS, live play back, object/motion detection and phone app on DEll Optiplex 3020


## Parts Needed:

### poe cameras
Recommended: ONVIF-compatible cameras (Blue Iris works best with ONVIF)


### mounting hardware
Outdoor junction boxes (optional but protects connections)
Screws, anchors, waterproof grommets

<img src="https://github.com/tarasermolenko/BlueIrisSetUpGuide/blob/main/camera.jpeg" alt="drawing" width="200"/>

###female netowrk cable adapters (make sure to find out if your wiring is A or B)

<img src="https://github.com/tarasermolenko/BlueIrisSetUpGuide/blob/main/femaleadapter.jpg" alt="drawing" width="200"/>


poe swtich

### Workstation
Dell Optiplex 3020 or similar

SSD for OS + Blue Iris database (HUGE performance difference)

Large HDD for video storage (2–4TB recommended)


## Software Used:

Blue Iris
Install normally



## Set Up Process:
After installation: enable “Run as a Service”
Prevents UI crashes from stopping recording
Keeps cameras working even after logoff or reboot

Intel QuickSync driver (for hardware-accelerated video decoding)
VLC (helps test RTSP streams)

## Connecting Cameras:

Option 1 – Managed PoE Switch

Log into switch web interface

Look at Connected Devices

Match MAC addresses with camera labels

Option 2 – Wireshark (for unmanaged switches)

Filter ARP packets:
arp

Turn each camera on one-at-a-time; IP will show

https://www.youtube.com/watch?v=V-KK36TRyaA

Option 3 – Router Device List

Most home routers show connected IP/MAC addresses

## Configure Cameras:
Access each camera in a browser:
http://CAMERA_IP

Log in with default credentials (change password!)

Set:

Static IP (recommended)

Correct timezone

Disable camera-side motion detection (Blue Iris will handle it)

Make sure RTSP/ONVIF is enabled

In blue iris 
set port to 80 when connecting camera (if getting not found error but ip addr work this is often the issue)

## Mounting:

<img src="https://github.com/tarasermolenko/BlueIrisSetUpGuide/blob/main/CamExample1.JPG" alt="drawing" width="200"/>

<img src="https://github.com/tarasermolenko/BlueIrisSetUpGuide/blob/main/CamExample2.JPG" alt="drawing" width="200"/>


## storage:
In Camera Settings → Record tab

Select: “Continuous + Alerts” OR “Motion-based recording”

Folder locations:

New folder = SSD (fast access)

Stored folder = HDD (long-term storage)

Recommended storage setup:

SSD for db + immediate recordings

HDD for archive footage

In Blue Iris Settings → Clips & archiving, set automatic move from SSD to HDD
