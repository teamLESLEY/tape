# Tape sensor libraries
To install, copy [`tape.hpp`](tape.hpp) to `include/` and
[`tape.cpp`](tape.cpp) to `src/` in the project.

## Table of Contents
- [API Reference](#api-reference)
  - [class **TapeSensor**](#class-tapesensor)
    - [Constructors](#constructors)
    - [Public member functions](#public-member-functions)

## API Reference
### class TapeSensor
Class for a tape sensor consisting of two reflectance
sensors. Designed to follow a dark tape on a light background.

#### Constructors
##### `TapeSensor`(PinName leftPin, PinName rightPin, unsigned int threshold)
##### `TapeSensor`(uint32\_t leftPin, uint32\_t rightPin, unsigned int threshold)
##### `TapeSensor`(PinName leftPin, uint32\_t rightPin, unsigned int threshold)
##### `TapeSensor`(uint32\_t leftPin, PinName rightPin, unsigned int threshold)
- **leftPin**: analogue input pin connected to the high side of the
  left reflectance sensor.
- **rightPin**: analogue input pin connected to the low side of the
  right reflectance sensor.
- **threshold**: the minimum sensor reading corresponding to a sensor
  being over the tape.

The two pins are set to input mode.

#### Public member functions
##### unsigned int `getLeftReading`()
Retrieve the raw analogue reading from the left tape sensor.

##### bool `isLeftOn`()
Returns true if the left tape sensor is over the tape.

##### unsigned int `getRightReading`()
Retrieve the raw analogue reading from the right tape sensor.

##### bool `isRightOn`()
Returns true if the right tape sensor is over the tape.

##### unsigned int `getThreshold`()
Returns the current minimum sensor reading corresponding to the
sensors being over the tape.

##### void `setThreshold`(unsigned int threshold)
Set the minimum sensor reading corresponding to the sensors being over
the tape.
