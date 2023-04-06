
# Hearing aids research under Raspberry Pi

_To provide intelligent voice assistants, sound source localization and tracking functions as well as basic sound gain and noise filtering functions._



<details id=0 open>
<summary><h2>About</h2></summary>

Existing hearing aid auditory frameworks provide basic sound amplification and crude noise filtering capabilities, limiting their growth in the existing AI technology market. 
This research results in increased hearing aid processing power and programmability for more sophisticated processing strategies to improve the quality of sound delivered to the impaired ear.

- ***What is included***: [Raspberry Pi 4B](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/), [ReSpeaker 4-MIC Array](https://wiki.seeedstudio.com/ReSpeaker_4_Mic_Array_for_Raspberry_Pi/), Headphone (Output), Screen, Remote controller
- ***What is new***: The core technical difference between the hearing aids studied in this experiment and ordinary hearing aids is the processing method inside the chip for the sound signals collected in by the microphone. 
- ***What will build***: Raspberry Pi-based hearing aids can be extended with software-controlled features to include Alexa voice assistant, sound source location and tracking, noise reduction, binaural processing, reverberation cancellation. 

  <div align=center><img width="876" height="400" src="https://github.com/WLi0777/Hearing-aids-research-under-Raspberry-Pi.io/blob/main/img/deliverable.png"/></div>

</details>

<details id=1>
<summary><h2>Step 1: Raspbian and ReSpeaker 4-Mic Array setup</h2></summary>
  
### :keyboard: Burn Raspbian on SD card (MacOS)

1. Go to [Raspberry Pi OS](https://www.raspberrypi.com/software/), obtain and install the .img file for Raspberry Pi Imager.
2. Go to [Index of Raspbian](https://downloads.raspberrypi.org/raspbian/images/), select 'raspbian-2020-02-14', download '2020-02-13-raspbian-buster.zip'.

     _The reason for not downloading the latest version is that ReSpeaker 4-Mic Array can only be adapted to the 2020-02-13 version of Raspbian._

3. Upload the file of Pi OS to Raspberry Pi Imager. Make sure to check the target location of the SD Card that is located on the home page of Raspberry Pi OS Imager. Click 'WRITE' to install.

    <div align=center><img width="613" height="241" src="https://github.com/WLi0777/Hearing-aids-research-under-Raspberry-Pi.io/blob/main/img/Raspberry%20Imaging.png"/></div>


### :keyboard: ReSpeaker 4-Mics Pi HAT setup

1. Download the Seeed voice card source code

```
sudo apt-get update
git clone https://github.com/Seeed-Projects/seeed-voicecard.git
cd seeed-voicecard
sudo ./install.sh --compat-kernel
reboot
```

2. Check that the sound card 
  
```
cd seeed-voicecard
arecord -L
```

The details of ReSpeaker 4-Mics voicecard will be displayed
  
<div align=center><img width="613" height="241" src="https://github.com/WLi0777/Hearing-aids-research-under-Raspberry-Pi.io/blob/main/img/Raspberry%20Imaging.png"/></div>

  
</details>
