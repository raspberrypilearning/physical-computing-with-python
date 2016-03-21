# Passive Infrared Motion Sensor (PIR)

Humans and other animals emit radiation all the time. This is nothing to be concerned about though, as the type of radiation we emit is called Infrared radiation (IR), which is pretty harmless at the levels emitted by humans. Infact, all objects above absolute zero (-273.15C) emit IR radiation.

A PIR sensor detects changes in the amount of IR radiation it receives. When there is a significant change in the amount of IR radiation it detects, then a pulse is triggered. This means that a PIR sensor can detect when a human moves infront of it (or indeed any animal).

![pir](images/pir_module.png)

## Wiring a PIR sensor.

The pulse emitted when a PIR detects motion needs to be amplified, and so it needs to be powered. There are three pins on the PIR, and they should be labled `Vcc`, `Gnd` and `Out`. If these labels aren't clear, they are sometimes concealed beneath the fresnel lens (the white cap), which you can temporarily remove to see the pin labels.

![wiring](images/pir_wiring.png)

1. As shown above, the `Vcc` pin needs attaching to a `5V` pin on the Raspberry Pi.
2. The `Gnd` pin on the PIR sensor can be attached to *any* ground pin on the Raspberry Pi.
3. Lastly the `Out` pin needs to be connected to any of the GPIO pins.

## Detecting Motion

You can detect motion with the PIR using the code below.

```python
from gpiozero import MotionSensor

pir = MotionSensor(4)

while True:
    if pir.motion_detected:
        print("You moved")
```
