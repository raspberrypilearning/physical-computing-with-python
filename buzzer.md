# Buzzers

There are two main types of buzzer - *active* and *passive*.

An *passive* buzzer emits a tone when a voltage is applied across it. A passive  buzzer requires a specific signal to generate a variety of tones. The *active* buzzers are a lot simpler to use, so these are covered here.

## Connecting a buzzer

An *active* buzzer can be connected just like an LED, but as they are a little more robust, you won't be needing a resistor to protect them.

Set up the circuit as shown below.

![buzzer](images/buzzer-circuit.png)

1. Add `Buzzer` to the `from gpiozero import...` line:

    ```python
    from gpiozero import Buzzer
	from time import sleep
    ```

1. Add a line below your creation of `button` and `lights` to add a `Buzzer` object:

    ```python
    buzzer = Buzzer(15)
    ```

1. In gpio zero, a `Buzzer` works exactly like an `LED`, so try adding a `buzzer.on()` and `buzzer.off()` into your loop:

    ```python
    while True:
        buzzer.on()
	    sleep(1)
        buzzer.off()

    ```

1. A `Buzzer` has a `beep()` method which works like an `LED`'s `blink`. Try it out:

    ```python
    while True:
        buzzer.beep()
    ```
