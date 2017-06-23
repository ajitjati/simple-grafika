# simple-grafika
Optimise camera recordings on-the-fly without FFMPEG or other heavy-weight libraries
Originally forked from https://github.com/google/grafika

## About Grafika

- A collection of hacks exercising graphics features.
- An SDK app, developed for API 18 (Android 4.3).  While some of the code
  may work with older versions of Android, no effort will be made to
  support them.
- Open source (Apache 2 license), copyright by Google.  So you can use the
  code according to the terms of the license (see "LICENSE").
- A perpetual work-in-progress.  It's updated whenever the need arises.

To some extent, Grafika can be treated as a companion to the
[Android System-Level Graphics Architecture](http://source.android.com/devices/graphics/architecture.html)
document.  The doc explains the technology that the examples rely on, and uses some of
Grafika's activities as examples.  If you want to understand how the code here works, start
by reading that.

But we have built a simplest version of demo which solves few major problems :
## About this sample-grafika
Attempts to record at 720p from the default camera, displaying the preview and recording it simultaneously.
- Recording continues until stopped.  If you back out and return, recording will start again,
  with a real-time gap.  If you try to play the movie while it's recording, you will see
  an incomplete file (and probably cause the play movie activity to crash).
- You can select a filter to apply to the preview.  It does not get applied to the recording.
  The shader used for the filters is not optimized, but seems to perform well on most devices
  (the original Nexus 7 (2012) being a notable exception).  Demo
  here: http://www.youtube.com/watch?v=kH9kCP2T5Gg
- The output is stored at home directory of your SD card ("grafika-2372377731.mp4").
- It can optimise your media/video on-the-fly from camera while recording
- You can change video key-frames, bitrates,framerates,size and encodings
- The best part is everything will happen on the fly so when your recording stops, the video should be already prepared :)
- You don't need FFMPEG or other heavy libraries to perform all the above tasks
- All code is written in the Java programming language -- the NDK is not used.
