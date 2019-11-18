# Introduction to Software Defined Radio

This repository contains labs to introduce the concept of software defined radio. Unlike conventional radio in SDR, a significant amount of processing is performed in software. After capturing a desired section of radio spectrum, say a region containing a radio station, the signal is digitised and demodulated in software.


## Hardware
For the labs we will use the DVB-T USB tuner which can be used as an SDR receiver.


## Software
1. Install the `rtl-sdr` driver following the intructions [here](https://osmocom.org/projects/rtl-sdr/wiki/Rtl-sdr)
1. Note that in the linux installation, you may need to run `cmake ../ -DINSTALL_UDEV_RULES=ON -DDETACH_KERNEL_DRIVER=ON` for the driver to work
1. Test the installation by using `rtl-fm` to listen to an FM station of your choice


## FM signal demodulation

The FM demodulation notebook introduces the examination of FM signals and their demodulation.

## ADB-S signals

ADB-S signals are broadcast by aeroplanes and can be decoded using the program [`dump1090`](https://github.com/MalcolmRobb/dump1090). Install this program on your system and explore the flights flying overhead. You should check flight details using the ICAO 24 bit address of the detected aircraft. These can be found on [https://www.flightradar24.com](https://www.flightradar24.com)

We will also examine the direct decoding of these signals.

1. Capture data from 1090MHz at a rate of 2MHz
`rtl_sdr -f 1090000000 -s 2000000 -g 50 output.bin`
1. Obtain the magnitudes of the samples.
1. Identify a region with a valid packet
