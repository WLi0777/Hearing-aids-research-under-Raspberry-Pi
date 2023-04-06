<!--
  <<< Author notes: Header of the course >>>
  Include a 1280×640 image, course title in sentence case, and a concise description in emphasis.
  In your repository settings: enable template repository, add your 1280×640 social image, auto delete head branches.
  Add your open source license, GitHub uses Creative Commons Attribution 4.0 International.
-->

# Hearing aids research under Raspberry Pi

_To provide intelligent voice assistants, sound source localization and tracking functions as well as basic sound gain and noise filtering functions._

<!--
  <<< Author notes: Start of the course >>>
  Include start button, a note about Actions minutes,
  and tell the learner why they should take the course.
  Each step should be wrapped in <details>/<summary>, with an `id` set.
  The start <details> should have `open` as well.
  Do not use quotes on the <details> tag attributes.
-->

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
1. Go to [Index of Raspbian](https://downloads.raspberrypi.org/raspbian/images/), select 'raspbian-2020-02-14', download '2020-02-13-raspbian-buster.zip'.

     _The reason for not downloading the latest version is that ReSpeaker 4-Mic Array can only be adapted to the 2020-02-13 version of Raspbian._

1. Upload the file of Pi OS to Raspberry Pi Imager. Make sure to check the target location of the SD Card that is located on the home page of Raspberry Pi OS Imager. Click 'WRITE' to install.


  
1. Click **Create pull request**.
1. In this pull request, go to the **Files changed** tab. We made an empty file `index.md` for you.
1. Select **Edit file** from the three dotted **...** menu in the upper right corner of the file view on `index.md`.
1. On the **Edit file** tab, add a `#`, followed by a **space**, before any content you like to make it an H1 Header. You can add more headers, using one to six `#` characters followed by a **space**.
1. Above your new content, click **Preview**.
1. At the bottom of the page, type a short, meaningful commit message that describes the change you made to the file.
1. Click **Commit changes**.
1.  Wait about 20 seconds then refresh this page for the next step.

</details>
