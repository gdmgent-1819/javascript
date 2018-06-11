---
layout: course
permalink: hardware/sensehat/
#
title: Sense Hat
title_long: Sense Hat
---

Inleiding
---------

De Sense Hat bevat:

- 8x8 RGB LED matrix;
- mini joystick;
- sensors:
  - Gyroscope;
  - Accelerometer;
  - Magnetometer;
  - Temperature;
  - Humidity;
  - Barometric pressure.

> **Links**
> - [Sense Hat Raspberry Pi documentation](https://www.raspberrypi.org/documentation/hardware/sense-hat/)
> - [Sense Hat documentation](https://pythonhosted.org/sense-hat/)
> - [Sense Hat API Reference](https://pythonhosted.org/sense-hat/api/)
> - [Electronisch schema Sense Hat](https://www.raspberrypi.org/documentation/hardware/sense-hat/images/Sense-HAT-V1_0.pdf)
{:.card.card-definition}

Installatie
-----------

De installatie van de Sense Hat-sdk is **"pretty straightforward"**. Zorg er eerst voor dat alle **APT**-paketten up-to-date zijn. Vervolgens installeren we het **sense-hat**-pakket. Na installatie van dit pakket herstarten we het besturingssysteem **Raspbian** op de Raspberry Pi 3.

{% highlight bash %}
sudo apt-get update
sudo apt-get install sense-hat
sudo reboot
{% endhighlight %}

Gebruik
-------

In de programmeertaal [Python](https://www.python.org/) kunnen we de reeds globaal geïnstalleerde Sense Hat-SDK aanspreken. We doen dit via het `from` en `import`-keyword. Dit betekent dat we de `SenseHat`-klasse gebruiken uit de `sense-hat`-naamruimte (namespace).

Vervorgens maken we een nieuwe instantie aan van deze `SenseHat`-klasse. Instantiëren betekent een actief object maken.

{% highlight py %}
from sense_hat import SenseHat

sense = SenseHat()

sense.show_message("Hello world!")
{% endhighlight %}

De `SenseHat`-klasse bevat een verzameling van publiek toegankelijke methoden die we kunnen aanspreken via de `.`-syntax gevolgd door de vermelding van de naam van deze methode, aangevuld met de vereiste argumenten.

In dit geval spreken we de methode (of functie) `show_message(...)` aan om een bericht te tonen op de RGB LED matrix.