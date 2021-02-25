<p align="center">
<img src="https://i.imgur.com/krtGcv6.png">
</p>

# myo-readings-dataset #
Myo armband electromyographic readings dataset for hibernation, flexion, extension, pronation, radial deviation, ulnar deviation, supination and fist gestures of the wrist. The sampling frequency is 200 Hz, as per Myo specs.

## Project structure ##
The readings are located in the _readings folder which contains one folder per recording session.
Each session folder contains multiple files, one per each wrist gesture. These are named &lt;label&gt;.txt (e. g. 1.txt for flexion, see Gesture labels below; each recording session folder should contain at least eight files).
The file itself it composed of multiple lines:

    ...
    11,32,-3,-43,4,5,42,7,0
    13,24,-5,12,43,42,12,1,0
    123,121,-100,-88,-32,32,123,13,1
	...
	
Each line represents the samples from the eight EMG channels on the Myo armband ([-128, 127], signed byte) as well as the label for the wrist gesture (class), separated by commas (there is no comma at the end of the line) in a given time moment. In this example the first two lines represent hibernation (e. g. 0 at the end of the line), while the third line represents flexion (e. g. 1). The EMG values are arbitrary in the example.

## Recording protocol ##
The Myo armband is placed on the thickest part of the forearm, with the LED pointing towards the dorsal (back) part of the hand.
Each file contains one minute of recordings. The labels at the end of the lines alternate between hiberation (0) and the gesture denoted in the file name every five seconds. The exception is the hibernation gesture, where the file contains only hibernation labels (0) at the end of the lines. Hibernation recordings contain various slight movements and motions of the hand that we would prefer to ignore during classification.

## Gesture labels ##
* 0: hibernation
	* <img height="100" src="https://i.imgur.com/LEv7vFR.jpg">
	* <img height="100" src="https://i.imgur.com/pCvJGau.jpg">
* 1: flexion
	* <img height="100" src="https://i.imgur.com/w56CXjb.jpg">
* 2: extension
	* <img height="100" src="https://i.imgur.com/vWoPmeW.jpg">
* 3: radial deviation
	* <img height="100" src="https://i.imgur.com/K5r091U.jpg">
* 4: ulnar deviation
	* <img height="100" src="https://i.imgur.com/cthd22A.jpg">
* 5: pronation
	* <img height="100" src="https://i.imgur.com/BAmN4af.jpg">
* 6: supination
	* <img height="100" src="https://i.imgur.com/p1G5uSI.jpg">
* 7: fist
	* <img height="100" src="https://i.imgur.com/zOTmjSb.jpg">
* <new_gesture_label>: <gesture_class_name>

