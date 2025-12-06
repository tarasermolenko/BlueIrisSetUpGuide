# BlueIris Set Up Guide & Notes

## Tested System:
6 1080p/720p cameras at 15-30 FPS on DEll Optiplex 3020 i7, live play back, object/motion detection

## Parts Needed:
SSD for OS + Blue Iris database

Large HDD for video storage (2TB min recommended)

ONVIF-compatible cameras (Blue Iris works best with ONVIF)

<img src="https://github.com/tarasermolenko/BlueIrisSetUpGuide/blob/main/camera.jpeg" alt="drawing" width="200"/>

POE swtich or injector

Female netowrk cable adapters (make sure to find out if your wiring is A or B)

<img src="https://github.com/tarasermolenko/BlueIrisSetUpGuide/blob/main/femaleadapter.jpg" alt="drawing" width="200"/>

Outdoor junction boxes (optional but protects connections)

<img src="https://github.com/tarasermolenko/BlueIrisSetUpGuide/blob/main/CamExample1.JPG" alt="drawing" width="200"/>

<img src="https://github.com/tarasermolenko/BlueIrisSetUpGuide/blob/main/CamExample2.JPG" alt="drawing" width="200"/>

## Software Set Up Process:
After installation: enable “Run as a Service”
  Prevents UI crashes from stopping recording
  Keeps cameras working even after logoff or reboot
  
Intel QuickSync driver (for hardware-accelerated video decoding)

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

Recommended: Set a static IP

## Configure Cameras:
Access each camera in a browser:
http://CAMERA_IP

Log in with default credentials (change password!)

Correct timezone

Disable camera-side motion detection (Blue Iris will handle it)

Make sure RTSP/ONVIF is enabled

In blue iris 
set port to 80 when connecting camera (if getting not found error but ip addr work this is often the issue)


## Storage:
In Camera Settings → Record tab

Select: “Continuous"


