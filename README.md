# Pico-Basics

Today we will review what we learn last time and practice blinking the onboard led. Click the following link for the website.

# **[CLICK HERE FOR PICO SIMULATOR](https://wokwi.com/projects/new/micropython-pi-pico)**

## Demonstration Code 

```python
import machine
import time

servoPin=15
servo=machine.PWM(machine.Pin(servoPin))
servo.freq(50)

potPin=26
pot=machine.ADC(machine.Pin(potPin))

while True:
    potVal=pot.read_u16()
    print(potVal)
    angle=180/65535*potVal
    writeVal=6553/180*angle + 1638
    servo.duty_u16(int(writeVal))
    time.sleep(.02)


```

## Example Code

### Hello World

Try typing the following example.

```python
print("Hello, World!")
```
### Basic Math with Variables

```python
# Define variables
a = 10
b = 5

# Perform arithmetic operations
sum_result = a + b
difference = a - b
product = a * b
quotient = a / b

# Output the results
print("Sum:", sum_result)
print("Difference:", difference)
print("Product:", product)
print("Quotient:", quotient)

```

## What are the pins on a Pico

![Alt Text](pico-pinout.png)

### Blinking the Onboard LED

```python
import machine
import time

# Initialize the onboard LED (GPIO 25)
led = machine.Pin(25, machine.Pin.OUT)

while True:
    led.value(1)      # Turn LED on
    time.sleep(0.5)   # Wait for 0.5 seconds
    led.value(0)      # Turn LED off
    time.sleep(0.5)   # Wait for 0.5 seconds

```

