# M4L_Ambisonics_Envelop4Live
Ambisonics tools for use in the lab, port from https://github.com/EnvelopSound/EnvelopForLive

![Logo](doc/E4L-banner.png)

[Envelop](http://envelop.us) is a nonprofit organization that amplifies the connective power of music through immersive listening spaces and open source spatial audio software. Three-dimensional experiences of sound and music bring people together, catalyzing shared moments of inspiration, empathy and wonder.

Envelop for Live (E4L) is an open source audio production framework for spatial audio composition and performance. Envelop for Live operates within the music production environment of Ableton Live 10 and Max for Live. Envelop for Live is designed to be a highly modular, flexible platform for artists to compose and perform spatial audio, and for developers to create new kinds of audio effects for the Ambisonics domain.

# Getting Started

E4L makes use of the advanced routing capabilities in [Live 10](https://www.ableton.com/en/live/) and [Max for Live](https://www.ableton.com/en/live/max-for-live/). Before continuing, make sure that you have installed both of these programs.

Please note that E4L is not officially supported on Windows. Max for Live is technically cross-platform, but some Windows users have reported issues with sporadic crashing and project corruption. We recommend working with macOS if possible. If experimenting with Windows, we encourage making regular backups and copies of project files.

## Installation

### For Users: Download

* Download the [latest release &rarr;](https://github.com/EnvelopSound/EnvelopForLive/releases/download/10.0.0/Envelop.for.Live.10.0.0.zip)
* Unzip the file and place the **Envelop for Live** folder in a good location on your hard drive

For easy access, you may wish to bookmark the **Envelop for Live** folder in the Places section of Ableton Live. Do this by dragging and dropping the folder, or using the "Add Folder..." button.

![Places](/doc/E4L-Places-Add.png)


## First Steps

The following [intro video](http://www.youtube.com/watch?v=iAHzJJhJVSQ) offers a quick overview of the Envelop for Live software.

[![Envelop for Live Software Intro](http://img.youtube.com/vi/iAHzJJhJVSQ/0.jpg)](http://www.youtube.com/watch?v=iAHzJJhJVSQ "Envelop for Live Software Intro")

### Create the E4L Master Bus

Create a new audio track. Add one of the **E4L Master Bus** device to this track. Note that the track will automatically be renamed to "E4L Master." It is recommended to leave this track name in place, though you may optionally rename it. This track and device will act as a receiver for Ambisonics audio, and allow you to monitor the output of a decoder.

<img src="/doc/E4L-Master-Bus.png" alt="E4L Master Bus" height="188" />

By default, the **E4L Master Bus** device will use a **Binaural** decoder, which enables you to preview your spatial mix on a pair of headphones. Make sure that the **Monitor 1+2** switch is engaged. Input meters on the **E4L Master Bus** device provide a visual reference for whether the device is receiving input.

### Add Source Tracks

Now, create a new audio or instrument track. In the track's effect chain, add the **E4L Source Panner** device. This device takes a stereo input and encodes it into 16 channels of high order ambisonics. This device automatically detects the master bus and uses Max for Live's routing capabilities to send its output to the E4L Master Bus.

<img src="/doc/E4L-Source-Panner.png" alt="E4L Source Panner" height="188" />

Note that by default, adding this device automatically sets the track's audio output routing to _Sends Only_. This is because E4L is already routing the Ambisonics-domain audio behind the scenes. Sending the stereo output from this track would result in two overlapping copies of the audio. For advanced use cases, you may override this setting and route the track output elsewhere (keep in mind that the track output sends only the stereo signal, not the 16-channel surround encoding).

Repeat this process to build up your surround mix. You may use as many **E4L Source Panner** devices as you like, on as many tracks as your CPU can handle.

## Custom IPEM Decoders
# 32-channel ambisonics dome: E4L Master Bus - 32 channel dome
Bavo created a 32-channel decoder for a dome structure.  Use the E4L Master Bus - 32 channel dome.amxd as master track. 

![Places](/doc/V2.png)

![Places](/doc/dome.jpg)

# Changing from IOSONO to Ambisonics
Check out this repo for "IOSONO replacements".  These devices can be swapped (file copy) with the original isono externals so the  automation and programming is not lost.  All devices send out 3rd order ambisonics to the master bus, which can decode the sound to the dome or the lab.


## Learn More
For more in-depth documentation and tutorials, see the [Envelop for Live Wiki](https://github.com/EnvelopSound/EnvelopForLive/wiki).
