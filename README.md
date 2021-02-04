<p align="center">
<img src="https://i.imgur.com/krtGcv6.png">
</p>

# myo-readings-dataset #
Myo armband electromyographic readings dataset for flexion, extension, pronation, supination, radial deviation, ulnar deviation, fist and hibernation gestures. The samping frequency is 200 Hz, as per Myo specs.

## Project structure ##
The readings are located in the _readings folder which contains one folder per recording session.
Each session contains multiple files, which are named &lt;label&gt;.txt (e. g. 3.txt for supination, see Gesture labels below; each recording session folder should contain at least eight files - for the eight different gestures).
The file itself it composed of multiple lines:

    11,32,-3,-43,4,5,42,7,7
    13,24,-5,12,43,42,12,1,7
    123,121,-100,-88,-32,32,123,13,3
	
Each line represents the samples from the eight EMG channels on the Myo armband ([-128, 127], signed byte) as well as the label for the gesture (class), separated by commas (there is no comma at the end of the line) in a given time moment. The pauses between the individual executions of gestures are labelled as hibernation. In this example the first two lines represent hibernation (e. g. 7), while the third line represents supination (e. g. 3; the EMG values are arbitrary in the example).

## Gesture labels ##
* 0: flexion
	* <img height="100" src="https://i.imgur.com/w56CXjb.jpg">
* 1: extension
	* <img height="100" src="https://i.imgur.com/vWoPmeW.jpg">
* 2: pronation
	* <img height="100" src="https://i.imgur.com/BAmN4af.jpg">
* 3: supination
	* <img height="100" src="https://i.imgur.com/p1G5uSI.jpg">
* 4: radial deviation
	* <img height="100" src="https://i.imgur.com/K5r091U.jpg">
* 5: ulnar deviation
	* <img height="100" src="https://i.imgur.com/cthd22A.jpg">
* 6: fist
	* <img height="100" src="https://i.imgur.com/zOTmjSb.jpg">
* 7: hibernation
	* <img height="100" src="https://i.imgur.com/LEv7vFR.jpg">
	* <img height="100" src="https://i.imgur.com/pCvJGau.jpg">
* <new_gesture_label>: <gesture_class_name>

