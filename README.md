
# Hearing aids research under Raspberry Pi

_To provide intelligent voice assistants, sound source localization and tracking functions as well as basic sound gain and noise filtering functions._



<details id=0 open>
<summary><h2>About</h2></summary>

Existing hearing aid auditory frameworks provide basic sound amplification and crude noise filtering capabilities, limiting their growth in the existing AI technology market. 
This research results in increased hearing aid processing power and programmability for more sophisticated processing strategies to improve the quality of sound delivered to the impaired ear.

- ***What is included***: [Raspberry Pi 4B](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/), [ReSpeaker 4-MIC Array](https://wiki.seeedstudio.com/ReSpeaker_4_Mic_Array_for_Raspberry_Pi/), Headphone (Output), Screen, Remote controller
- ***What is new***: The core technical difference between the hearing aids studied in this experiment and ordinary hearing aids is the processing method inside the chip for the sound signals collected in by the microphone. 
- ***What will build***: Raspberry Pi-based hearing aids can be extended with software-controlled features to include Alexa voice assistant, sound source location and tracking, noise reduction, binaural processing, reverberation cancellation. 

<p align="center">
<img alt="Deliverable" src=https://github.com/WLi0777/Hearing-aids-research-under-Raspberry-Pi.io/blob/main/img/Deliverables.png width=876 hight=412>
 

</details>

<details id=1>
<summary><h2>Step 1: Raspbian and ReSpeaker 4-Mic Array setup</h2></summary>
  
### :floppy_disk: Burn Raspbian on SD card (MacOS)

1. Go to [Raspberry Pi OS](https://www.raspberrypi.com/software/), obtain and install the .img file for Raspberry Pi Imager.
2. Go to [Index of Raspbian](https://downloads.raspberrypi.org/raspbian/images/), select 'raspbian-2020-02-14', download '2020-02-13-raspbian-buster.zip'.

     _The reason for not downloading the latest version is that ReSpeaker 4-Mic Array can only be adapted to the 2020-02-13 version of Raspbian._

3. Upload the file of Pi OS to Raspberry Pi Imager. Make sure to check the target location of the SD Card that is located on the home page of Raspberry Pi OS Imager. Click 'WRITE' to install.

 <p align="center">  
 <img alt="Imager" src=https://github.com/WLi0777/Hearing-aids-research-under-Raspberry-Pi.io/blob/main/img/Raspberry%20Imaging.png width=606 hight=238>

&nbsp;
###  :sound: ReSpeaker 4-Mics Pi HAT setup

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
    

    The details of soundcard should show like this:




    ```
    pi@raspberrypi:~ $ cd seeed-voicecard
    pi@raspberrypi:~/seeed-voicecard $ arecord -L
    null
        Discard all samples (playback) or generate zero samples (capture)
    jack
        JACK Audio Connection Kit
    pulse
        PulseAudio Sound Server
    default
    playback
    ac108
    usbstream:CARD=b1
        bcm2835 HDMI 1
        USB Stream Output
    usbstream:CARD=Headphones
        bcm2835 Headphones
        USB Stream Output
    sysdefault:CARD=seeed4micvoicec
        seeed-4mic-voicecard, bcm2835-12s-ac10x-codeco ac10x-codec@-0
        Default Audio Device
    dmix:CARD=seeed4micvoicec,DEV=0
        seeed-4mic-voicecard, bcm2835-12s-ac10x-codeco ac10x-codec@-0
        Direct sample mixing device
    dsnoop:CARD=seeed4micvoicec,DEV=0
        seeed-4mic-voicecard, bcm2835-12s-ac10x-codeco ac10x-codec@-0
        Direct sample snooping device
    hw:CARD=seeed4micvoicec,DEV=0
        seeed-4mic-voicecard, bcm2835-12s-ac10x-codeco ac10x-codec@-0
        Direct hardware device without any conversions
    plughw:CARD=seeed4micvoicec,DEV=0
        seeed-4mic-voicecard, bcm2835-12s-ac10x-codeco ac10x-codec@-0
        Hardware device with all software conversions
    usbstream:CARD=seeed4micvoicec
        seeed-4mic-voicecard
        USB Stream Output
    ```



3. Adjust the microphone volume

    ```
    alsamixer
    ``` 
  
<p align="center">
<img alt="AlsaMixer" src=https://github.com/WLi0777/Hearing-aids-research-under-Raspberry-Pi.io/blob/main/img/AlsaMixer.png width=569 hight=340>


4. Install audacity for recording
  
    ```
    sudo apt update
    sudo apt install audacity 
    audacity
    ``` 
  
<p align="center">
<img alt="audacity" src=https://github.com/WLi0777/Hearing-aids-research-under-Raspberry-Pi.io/blob/main/img/audacity.png width=510 hight=376>
  

 5. Raspberry Pi configuration setup 
     Set Headphone as output, SPI SSH and I2C to be enabled.
 
 6. Check number
 
    ```
    arecord -l
    ``` 
 
    ```
    pi@raspberrypi:~ $ arecord -l
    **** List of CAPTURE Hardware Devices ****
    card 2: seeed4micvoicec [seeed-4mic-voicecard], device 0: bcm2835-i2s-ac10x-code
    c0 ac10x-codec0-0 [bcm2835-i2s-ac10x-codec0 ac10x-codec0-0]
      Subdevices: 1/1
      Subdevice #0: subdevice #0
    ``` 
    

    :pushpin: Voicecard represents as **hw:2,0**
&nbsp;



    ```
    aplay -l
    ``` 

    

   

    


</details>
