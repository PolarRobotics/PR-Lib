# PR-Lib

## Location for all Polar Robotics Libraries
These are files that regular programming team members should not need to change but can utilize in their current projects  
Once a library is included just create an object to reference and call the functions listed below.

## Libraries Included:
- Motor Control
- Lights
- Pairing

## Motor Control Details:
Used for controlling motors using the ESP (Implements parts of the SERVO Library to handle PWM signals)  
*A servo-based PWM library for the ESP32, utilizing hardware PWM drivers via ledc*  
The main functions that most people should need to use are listed below, but there are some other functions that you may also use **(Look through the actual code for these)**
```
void MotorControl::write(float pwr)
uint8_t MotorControl::attach(int pin)
void MotorControl::writelow()
```

## Lights Details:
Used for controlling the lights using the ESP *Includes the FastLED Library and builds on it*  
The main functions to use are listed below **(Read the actual code for more details if needed)**
```
void Lights::setupLEDS()
void Lights::setLEDStatus(LEDState status)
void Lights::togglePosition()
int Lights::returnStatus()
```

**There is also an ENUM for LEDState with the following values**
```
 enum LEDState {
        PAIRING,     // Yellow
        PAIRED,      // green then fade out
        NOTPAIRED,
        OFFENSE,     // blue and green
        DEFENSE,     // green
        TACKLED,     // turn red when tackled
        OFF
    }; 
```

## Pairing Details:
Used for pairing the PS5 controllers to the robots  
The main functions to use are listed below **(Read the actual code for more details if needed)**
```
void activatePairing(bool doRePair, int discoverTime)
```
