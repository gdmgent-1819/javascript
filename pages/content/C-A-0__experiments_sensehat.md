---
layout: course
permalink: experiments/sensehat/
#
title: SenseHat
title_long: SenseHat
---

Temperature
-----------

### Code

{% highlight py %}
from sense_hat import SenseHat
import random
from math import floor, ceil
import time

sense = SenseHat()

color_blue = (0, 0, 255)
color_black = (0, 0, 0)

while True:
    pattern = ""
    matrix = []
    for r in range(0,8):
        temp = ""
        for c in range(0, 4):
            temp = temp + str(round(random.random()))

        temp = temp + temp[::-1]
        pattern = pattern + temp                   
                    
    for p in range(0,64):
        bit = int(pattern[p])
        color = color_blue if bit == 1 else color_black
        matrix.append(color)
        
    sense.set_pixels(matrix)
    time.sleep(3)
{% endhighlight %}


Arcade Characters
-----------------

### Inleiding

In dit experiment trachten we een 8x8-bit arcade character aan te maken via de 8x8-matrix aanwezig op de Sense Hat. We willen ook dat om de 3 seconden een uniek (lees random) character aangemaakt zal worden.

Zo'n character bevat een horizontale of vertikale spiegeling. Dit wil zeggen dat we vier digits zullen spiegelen of omdraaien per rij.

### Code

{% highlight py %}
from sense_hat import SenseHat
import random
from math import floor, ceil
import time

sense = SenseHat()

color_blue = (0, 0, 255)
color_black = (0, 0, 0)

while True:
    pattern = ""
    matrix = []
    for r in range(0,8):
        temp = ""
        for c in range(0, 4):
            temp = temp + str(round(random.random()))

        temp = temp + temp[::-1]
        pattern = pattern + temp                   
                    
    for p in range(0,64):
        bit = int(pattern[p])
        color = color_blue if bit == 1 else color_black
        matrix.append(color)
        
    sense.set_pixels(matrix)
    time.sleep(3)
{% endhighlight %}
