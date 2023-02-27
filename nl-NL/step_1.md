Gebruik `blink` om kleuren te wisselen in een RGB LED.

Een LED laten knipperen:

--- code ---
---
language: python
line_numbers: false
---
rgb.blink() # red for 1 second, green for 1 second, blue for 1 second print("Blinking") # Runs immediately

sleep(6) rgb.off() --- /code ---

Knipper aan en uit tussen een enkele kleur en uit `(0, 0, 0)`:

--- code ---
---
language: python
line_numbers: false
---
# 2 seconden paars knipperen, 0,5 seconden uit
rgb.blink(on_times=(2, 0.5), colors=((255, 0, 255), (0, 0, 0)), wait=True, n=3) print("Finished blinking") # Runs after 3 repeats --- /code ---

Een vast aantal keren knipperen, met verschillende tijden en kleuren:

--- code ---
---
language: python
line_numbers: false
---
# blink red 1 second, green 0.5 seconds, blue 0.25 seconds
rgb.blink((1, 0.5, 0.25), colors=((255, 0, 0), (0, 255, 0), (0, 0, 255)), wait=True, n=2) print("Finished blinking") # Runs after 2 blink repeats

--- /code ---

**Tip:** Als je geen aparte off_time hebt ingesteld zal deze hetzelfde zijn als on_time.

Gebruik `pulse` om geleidelijk de helderheid van een RGB LED te veranderen:

--- code ---
---
language: python
line_numbers: false
---
rgb.pulse() # pulse red for 1 second, green for 1 second, blue for 1 second print("Pulsing") # Runs immediately

--- /code ---

Bestuur de pulssnelheid tussen een kleur en uit `(0, 0, 0)` met een vast aantal herhalingen:

--- code ---
---
language: python
line_numbers: false
---
# 2 seconden om te vervagen van paars naar uit, 0,5 seconden om van uit naar paars te schakelen
rgb.pulse(fade_times=(2, 0.5), colors=((255, 0, 255), (0, 0, 0)), wait=True, n=3) print("Finished pulsing") # Runs after 3 pulses

--- /code ---

Gebruik `cycle` om geleidelijk over te schakelen tussen kleuren:

--- code ---
---
language: python
line_numbers: false
---
rgb.cycle() # Gradually colour cycle through colours between red and green, green and blue then blue and red print("Cycle") # Runs immediately

--- /code ---

Regel de kleur, tijdsduur en herhalingen:

--- code ---
---
language: python
line_numbers: false
---
# Kleurcyclus langzamer in de tegenovergestelde richting
rgb.cycle(fade_times=3, colors=((0, 0, 255), (0, 255, 0), (255, 0, 0)), wait=True, n=2) rgb.off()

--- /code ---

**Tip:** `blink` en `pulse` en `cycle` worden uitgevoerd totdat `off` wordt aangeroepen of tot `blink`, `pulse` of `cycle` worden aangeroepen met nieuwe instellingen. Gebruik `wait=True` en stel `n` in om een vast aantal keren te knipperen of te pulseren. 
