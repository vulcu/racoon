# Racoon - Bluetooth Stereo Amplifier #
A bluetooth-based amplifier iterating on the [Opossum](https://github.com/vulcu/opossum) project, written primarily C/C++ for a specific hardware platform comprised of:
  * [Nordic nRF52832 Bluetooth 5.2 SoC](https://www.nordicsemi.com/Products/nRF52832)
  * [Infineon Technologies MA12070P Integrated Audio Amplifier](https://www.infineon.com/cms/en/product/power/class-d-audio-amplifier-ic/integrated-class-d-audio-amplifier-ics/ma12070p/)
  * [Cirrus Logic CS5343 Stereo A/D Converter](https://www.cirrus.com/products/cs5343-44/)
  * [Cirrus Logic CS4344 Stereo D/A Converter](https://www.cirrus.com/products/cs4344-45-48/)

## Table of Contents ##
* [General Info](#general-info)
* [Features](#features)
* [Remaining Work](#remaining-work)

## General Info ##
This project is the 2nd gen evolution of a bluetooth stereo audio amplifier with a spetral-based automatic gain control. [The 1st generation](https://www.github.com/vulcu/opossum) was concieved and started at a point before I had access to an online streaming service such as Spotify, who normalizes track levels across albums and artists. When playing back music without that normalization it often frustrated me when a quiet track would follow a loud track, or vice versa, and the playback volume would thus jump substantially in one direction or the other.

A bluetooth-connected amplifier utilizing a microcontroller continuously analyzing the audio spectrum and adjusting the playback amplifier volume accordingly, solves the issue!

## Features ##
All [1st generation](https://www.github.com/vulcu/opossum) features maintained, plus the 2nd generation of this will platform will:
* Streamline the platform from a hardware design perspective
  * unified BT+DSP system
  * digital audio volume control (no predefined gain steps)
  * custom PCBA minimizes size and increases reliability over 1st gen dev board solution
  * project is much more easily replicated
* Add line-in/line-out functionality
* Possibly add a display for displaying system and/or playback information
* Expand EQ and DSP options beyond simple on/off functionality

#### Remaining Work ####
* Bring up hardware hardware system
  * power control
  * GPIO
    * mute
      * line-in
      * line-out
      * amplifier
  * I2C/SPI
    * amplifier
  * bluetooth radio
    * establish BT connection
    * establish audio streaming
  * I2S audio system
    * ADC
    * DAC
    * Amplifier
  * display (_not yet defined_)
    * establish connectivity
    * display text
    * display images
* route basic DSP (steel thread)
  * BT/line-in audio is routed to amplifier
  * BT/line-in audio is routed to DAC
  * ADC audio is selected over BT audio if
    * Line input is active
    * BT connection/A2DP is either not established or audio is not streaming
* port User Experience from [Opossum](https://www.github.com/vulcu/opossum) to use as a starting point
  * port DSP processing (automatic gain control)
  * port User Interface
    * Buttons
    * Volume Control
    * LED Control

#### Status: This project is in the pre-development stage. ####

## ##
(C) 2021-2021, Winry R. Litwa-Vulcu

