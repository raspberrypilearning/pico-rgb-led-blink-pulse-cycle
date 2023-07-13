Gebruik `blink` om kleuren te wisselen in een RGB LED.

Een LED laten knipperen:

--- code ---
---
language: python
line_numbers: false
---
rgb.blink() # Rood gedurende 1 seconde, groen gedurende 1 seconde, blauw gedurende 1 seconde 
print("Knipperen") # Taak onmiddellijk uitvoeren

sleep(6) 
rgb.off()
--- /code ---

Knipper aan en uit tussen een enkele kleur en uit `(0, 0, 0)`:

--- code ---
---
language: python
line_numbers: false
---
# 2 seconden paars knipperen, 0,5 seconden uit
rgb.blink(on_times=(2, 0.5), colors=((255, 0, 255), (0, 0, 0)), wait=True, n=3) 
print("Knipperen voltooid") # Voert de taak uit na 3 herhalingen

--- /code ---

Een vast aantal keren knipperen, met verschillende tijden en kleuren:

--- code ---
---
language: python
line_numbers: false
---
# 1 seconde rood, 0,5 seconde groen en 0,25 seconden blauw knipperen
rgb.blink((1, 0.5, 0.25), colors=((255, 0, 0), (0, 255, 0), (0, 0, 255)), wait=True, n=2) 
print("Knipperen voltooid") # Taak uitvoeren na 2 keer knipperen

--- /code ---

**Tip:** Als je geen aparte off_time hebt ingesteld zal deze hetzelfde zijn als on_time.

Gebruik `pulse` om geleidelijk de helderheid van een RGB LED te veranderen:

--- code ---
---
language: python
line_numbers: false
---
rgb.pulse() # Pulse rood gedurende 1 seconde, groen gedurende 1 seconde, blauw gedurende 1 seconde 
print("Pulseren") # Taak onmiddellijk uitvoeren

--- /code ---

Bestuur de pulssnelheid tussen een kleur en uit `(0, 0, 0)` met een vast aantal herhalingen:

--- code ---
---
language: python
line_numbers: false
---
# 2 seconden om te vervagen van paars naar uit, 0,5 seconden om van uit naar paars te veranderen
rgb.pulse(fade_times=(2, 0.5), colors=((255, 0, 255), (0, 0, 0)), wait=True, n=3) 
print("Pulseren voltooid") # Voert de taak uit na 3 pulsen

--- /code ---

Gebruik `cycle` om geleidelijk over te schakelen tussen kleuren:

--- code ---
---
language: python
line_numbers: false
---
rgb.cycle() # Geleidelijke kleurcyclus door kleuren tussen rood en groen, groen en blauw, dan blauw en rood 
print("Knipperen") # Taak onmiddellijk uitvoeren

--- /code ---

Regel de kleur, tijdsduur en herhalingen:

--- code ---
---
language: python
line_numbers: false
---
# Kleurcyclus langzamer in de tegenovergestelde richting
rgb.cycle(fade_times=3, colors=((0, 0, 255), (0, 255, 0), (255, 0, 0)), wait=True, n=2) 
rgb.off()

--- /code ---

**Tip:** `blink` en `pulse` en `cycle` worden uitgevoerd totdat `off` wordt aangeroepen of tot `blink`, `pulse` of `cycle` worden aangeroepen met nieuwe instellingen. Gebruik `wait=True` en stel `n` in om een vast aantal keren te knipperen of te pulseren.
