<p align="center">
<img src="https://i.imgur.com/aY3xbJX.png">
<img src="https://i.imgur.com/1V09QQU.png">
</p>

# myo-readings-dataset #
Myo armband electromyographic readings dataset for hibernation, flexion, extension, radial deviation, ulnar deviation, pronation, supination and fist gestures of the wrist.

## Project structure ##
The readings are located in the _readings folder which contains one folder per recording session.
Each session folder contains multiple files, one per each wrist gesture. These are named &lt;label&gt;.txt (e. g. 2.txt for extension, see Gesture labels below). Each recording session folder should contain at least eight files (for gestures 0-7).
The file itself it composed of multiple lines:

    ...
    11,32,-3,-43,4,5,42,7,0
    13,24,-5,12,43,42,12,1,0
    123,121,-100,-88,-32,32,123,13,2
	...
	
Each line represents the samples from the eight EMG channels on the Myo armband ([-128, 127], signed byte) as well as the label for the wrist gesture (class) in a given time moment, separated by commas. There is no comma at the end of the line and there should be no spaces anywhere in the file. The sampling frequency is approximately 200 Hz, as per Myo specifications. In this example, the first two lines represent hibernation (e. g. 0 at the end of the line), while the third line represents extension (e. g. 2). The EMG values are arbitrary in the example. There should not be an empty line at the end of the file.

## Recording protocol ##
The Myo armband is placed on the thickest part of the right forearm, with the LED pointing towards the dorsal (back) part of the hand.
Each file contains one minute of recordings and should be around 12 000 lines long (~200 Hz &times; 60 s = 12 000). The labels at the ends of the lines alternate between hiberation (0) and the gesture denoted in the file name every five seconds. The exception is the hibernation gesture, where the file contains only hibernation labels (0) at the ends of the lines. Hibernation recordings contain various slight movements and motions of the hand that we would prefer to ignore during classification.

## Gesture labels ##
* 0: hibernation
	* <img height="100" src="https://i.imgur.com/wIaBTrp.png">
	* <img height="100" src="https://i.imgur.com/EHSFyVX.png">
* 1: flexion
	* <img height="100" src="https://i.imgur.com/sp4wWX3.png">
* 2: extension
	* <img height="100" src="https://i.imgur.com/WtojDBg.png">
* 3: radial deviation
	* <img height="100" src="https://i.imgur.com/lsqb881.png">
* 4: ulnar deviation
	* <img height="100" src="https://i.imgur.com/ypGlBKi.png">
* 5: pronation
	* <img height="100" src="https://i.imgur.com/TQmps6o.png">
* 6: supination
	* <img height="100" src="https://i.imgur.com/oIPhfVB.png">
* 7: fist
	* <img height="100" src="https://i.imgur.com/1DTqj5Y.png">

## Optional gesture labels ##
* 8: sign of the horns
	* <img height="100" src="https://i.imgur.com/IhPe0pz.png">
* <new_gesture_label>: <new_gesture_class_name>
	* <new_gesture_image>
