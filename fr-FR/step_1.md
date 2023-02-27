Utilise `blink` pour passer d'une couleur à l'autre sur une LED RVB.

Faire clignoter une LED :

--- code ---
---
language: python
line_numbers: false
---
rgb.blink() # Rouge pendant 1 seconde, vert pendant 1 seconde, bleu pendant 1 seconde
print("Clignotant") # S'exécute immédiatement

sleep(6)
rgb.off()

--- /code ---

Clignotement allumé et éteint entre une seule couleur et éteint `(0, 0, 0)`:

--- code ---
---
language: python
line_numbers: false
---
# Clignotement violet 2 secondes, éteint 0,5 seconde
rgb.blink(on_times=(2, 0.5), colors=((255, 0, 255), (0, 0, 0)), wait=True, n=3) 
print("Clignotement terminé") # Exécuter après 3 répétitions
--- /code ---

Clignote un nombre fixe de fois, avec des durées et des couleurs différentes :

--- code ---
---
language: python
line_numbers: false
---
# Clignotement rouge 1 seconde, vert 0,5 seconde, bleu 0,25 seconde
rgb.blink((1, 0.5, 0.25), colors=((255, 0, 0), (0, 255, 0), (0, 0, 255)), wait=True, n=2) 
print("Clignotement terminé") # Fonctionne après 2 répétitions de clignotement

--- /code ---

**Astuce :** Si tu ne définis pas off_time, ce sera le même que pour on_time.

Utilise `pulse` pour modifier progressivement la luminosité et la couleur d'une LED RVB :

--- code ---
---
language: python
line_numbers: false
---
rgb.pulse() # Pulse rouge pendant 1 seconde, vert pendant 1 seconde, bleu pendant 1 seconde 
print("Pulsation") # S'exécute immédiatement

--- /code ---

Contrôle la vitesse d'impulsion entre une couleur et off `(0, 0, 0)` avec un nombre fixe de répétitions :

--- code ---
---
language: python
line_numbers: false
---
# 2 secondes pour passer du violet à éteint, 0,5 seconde pour passer d'éteint au violet
rgb.pulse(fade_times=(2, 0.5), colors=((255, 0, 255), (0, 0, 0)), wait=True, n=3) 
print("Pulsation terminée") # Fonctionne après 3 impulsions

--- /code ---

Utilise `cycle` pour passer progressivement d'une couleur à l'autre :

--- code ---
---
language: python
line_numbers: false
---
rgb.cycle() # Progressivement, faites défiler les couleurs entre le rouge et le vert, le vert et le bleu puis le bleu et le rouge 
print("Cycle") # S'exécute immédiatement

--- /code ---

Contrôle la couleur, les temps et les répétitions :

--- code ---
---
language: python
line_numbers: false
---
# Cycle de couleur plus lent dans la direction opposée
rgb.cycle(fade_times=3, colors=((0, 0, 255), (0, 255, 0), (255, 0, 0)), wait=True, n=2) 
rgb.off()

--- /code ---

**Astuce :** `blink`, `pulse` et `cycle` fonctionneront jusqu'à ce que `off` soit appelé ou `blink`, `pulse` ou `cycle` soient appelés avec de nouveaux réglages. Utilise `wait=True` et régle `n` pour clignoter ou pulser un nombre fixe de fois.
