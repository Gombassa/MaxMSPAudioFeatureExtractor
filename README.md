# MaxMSPAudioFeatureExtractor
An audio analyzer for Win64 using sigmund~

https://github.com/Gombassa/MaxMSPAudioFeatureExtractor

This is Max/MSP feature extractor patcher, intended for use with Wekinator for the Kadenze Machine Learning for Artists and Musicians course, assignment 5. It is intended to be
used to extract basic features like pitch and envelope from a live audio source, output as packaged OSC messages. It may offer a solution for students and others using Max/MSP 
on win64(the more ubiquitous analyzer~ with its more extensive feature set, is win32 only at present).

To use:

Install the sigmund~ external object in Max/MSP from http://vboehm.net/2015/06/a-64-bit-version-of-sigmund/

Set your live audio source input in the Options>Audio Status window.

Adjust the slider to prevent clipping

The gate is set very conservatively and need not be adjusted; it should simply close on a null signal.

Adjust the @hop argument in sigmund~ to set the time between messages in ms.

The @growth argument also serves as a kind of crude gate, so adjusting this can also reduce low level noise for the env output.

To do:
Figure out why the pitch output always defaults to a value of -1500.
Clamp both pitch and env to 0-127 value range (should be easier on Wekinator).
