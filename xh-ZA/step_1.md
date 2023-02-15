Use `blink` change between colours on an RGB LED.

Blink an LED:

--- code ---
---
language: python
line_numbers: false
---
rgb.blink() # red for 1 second, green for 1 second, blue for 1 second print("Blinking") # Runs immediately

sleep(6) rgb.off() --- /code ---

Blink on and off between a single colour and off `(0, 0, 0)`:

--- code ---
---
language: python
line_numbers: false
---
# blink purple 2 seconds, off 0.5 seconds
rgb.blink(on_times=(2, 0.5), colors=((255, 0, 255), (0, 0, 0)), wait=True, n=3) print("Finished blinking") # Runs after 3 repeats --- /code ---

Blink a fixed number of times, with different timings and colours:

--- code ---
---
language: python
line_numbers: false
---
# blink red 1 second, green 0.5 seconds, blue 0.25 seconds
rgb.blink((1, 0.5, 0.25), colors=((255, 0, 0), (0, 255, 0), (0, 0, 255)), wait=True, n=2) print("Finished blinking") # Runs after 2 blink repeats

--- /code ---

**Tip:** If you don't set off_time then it will be the same as on_time.

Use `pulse` to gradually change the brightness and colour of an RGB LED:

--- code ---
---
language: python
line_numbers: false
---
rgb.pulse() # pulse red for 1 second, green for 1 second, blue for 1 second print("Pulsing") # Runs immediately

--- /code ---

Control the pulse speed between a colour and off `(0, 0, 0)` with a fixed number of repeats:

--- code ---
---
language: python
line_numbers: false
---
# 2 second to fade from purple to off, 0.5 seconds to change from off to purple
rgb.pulse(fade_times=(2, 0.5), colors=((255, 0, 255), (0, 0, 0)), wait=True, n=3) print("Finished pulsing") # Runs after 3 pulses

--- /code ---

Use `cycle` to gradually change between colours:

--- code ---
---
language: python
line_numbers: false
---
rgb.cycle() # Gradually colour cycle through colours between red and green, green and blue then blue and red print("Cycle") # Runs immediately

--- /code ---

Control the colour, times and repeats:

--- code ---
---
language: python
line_numbers: false
---
# Colour cycle slower in the opposite direction
rgb.cycle(fade_times=3, colors=((0, 0, 255), (0, 255, 0), (255, 0, 0)), wait=True, n=2) rgb.off()

--- /code ---

**Tip:** `blink`, `pulse` and `cycle` will run until `off` is called or `blink`, `pulse` or `cycle` are called with new settings. Use `wait=True` and set `n` to blink or pulse a fixed number of times. 
