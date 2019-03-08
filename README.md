# Introduction

This repo contains:

* The Arduino sketch for the Dimmer device (Arduino folder)
* The schematic for the additional PCB (hw folder)
* The Unity3D plugin (Unity folder)

# Setup

## Arduino

Download the Arduino IDE (https://www.arduino.cc) and follow the usual Arduino
procedures as described at https://www.arduino.cc/en/Guide/ArduinoUno.

## Unity3D

Copy the content of the `Unity` folder to your project's assets. Copy
`gyroSettings.json` to the root folder of your project. Be sure to set the
right value for `_serialPort`.

If you build your project copy `gyroSettings.json` to the root folder of the build.

# Usage

## Arduino

The Arduino operates on a request-response based protocol. Currently, the
following requests are implemented:
* `g` gets the gyroscope values as a tab separated list (yaw-pitch-roll)
* `j` gets the state of digital pin 13
* `a` (experimental) gets the acceleration values in all three axis as a tab separated list
* `q` (experimental) gets the gyroscope values as a tab separated list quaternion
* `i` (debug purpose) always returns `true`

## Unity

1. Add `ArduinoGyro.cs` to your scene
1. Set `_controlPosition` to the object you would like to control through the
   gyroscope

The rest of the parameters have no effect, as they are not implemented yet.
