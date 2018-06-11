---
layout: course
permalink: hardware/raspbian/
#
title: Raspbian
title_long: Raspbian
---

Inleiding
---------

We zullen gebruik maken van een SD-kaart waarop [NOOBS](https://www.raspberrypi.org/documentation/installation/noobs.md) geïnstalleerd is. NOOBS staat voor **New Out Of the Box Software** en wordt gebruikt om bepaalde besturingssystemen te installeren voor de Raspberry Pi. Vanaf NOOBS v1.3.10 bevat deze installatiemanager enkel het **[Raspbian](http://raspbian.org/)** Operating System. Om een ander besturingssysteem te installeren hebben we netwerkconnectie nodig.

Start je met een **lege SD-kaart**, dan moet je:

- SD-kaart formatteren;
- [NOOBS downloaden](https://www.raspberrypi.org/downloads/noobs/);
- Het gedownload archiveerbestand uitpakken;
- Kopiëren van alle uitgepakte bestanden onder de root van de SD-kaart.

Op **17-08-2017** draagt NOOBS de versie **v2.4.3**.

Installatie Raspbian besturingssysteem
--------------------------------------

Zoals we al eerder vertelden bevat de NOOBS installatiemanager het **Raspbian** besturingssysteem. Wil je niet gebruik maken van NOOBS, dan moet je [Raspbian-image](https://www.raspberrypi.org/downloads/raspbian/) zelf downloaden en de [installatieprocedure](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) volgen via de officiële Raspberry Pi-website.

We selecteren via NOOBS het Raspbian besturingsysteem en stellen de taal **Nederlands** en de toetsenbordindeling **be** in.

{% include shared/figure.html src="http://www.arteveldehogeschool.be/campusGDM/wanm/1718/syllabi/1718-wot/IMG_20170904_134136.jpg" alt="Installatie Raspbian" caption="Installatie Raspbian" %}

Raspbian is een gratis besturingssysteem gebasseerd op [Debian](https://www.debian.org/index.nl.html) en geoptimaliseerd voor de Raspberry Pi. Het **Raspbian** besturingssysteem bevat ongeveer 35000 pre-compiled packages, waaronder:

- Python;
- Scratch;
- Sonic Pi;
- Java;
- Mathematica (Wolfram Language);
- Minecraft;
- ... .

Na de installatie start het besturingssysteem automatisch op.

{% include shared/figure.html src="http://www.arteveldehogeschool.be/campusGDM/wanm/1718/syllabi/1718-wot/IMG_20170904_140417.jpg" alt="Installatie Raspbian voltooid" caption="Installatie Raspbian voltooid" %}

Vervolgens gaan selecteren we et **Artevelde HS Open** wifi-netwerk via het netwerk-icoon op de Raspbian-desktop. Start vervolgens de **Chromemium webbrowser** via de **Raspbian startknop &gt; Internet &gt; Chromium Web Browser**. Log vervolgens in met je Arteveldehogeschool-account.

{% include shared/figure.html src="http://www.arteveldehogeschool.be/campusGDM/wanm/1718/syllabi/1718-wot/IMG_20170904_150354.jpg" alt="Chromium webbrowser" caption="Chromium webbrowser" %}

Update &amp; Upgrade
--------------------

Nadat we geconnecteerd zijn met het Internet gaan we alle [paketten updaten](https://www.raspberrypi.org/documentation/raspbian/updating.md) die aanwezig zijn op het besturingssysteem. Dit kan eenvoudigweg door het volgende commando uit te voeren via de terminal (zwart icoon in de top-bar):

{% highlight bash %}
sudo apt-get update
{% endhighlight %}

{% include shared/figure.html src="http://www.arteveldehogeschool.be/campusGDM/wanm/1718/syllabi/1718-wot/IMG_20170904_150446.jpg" alt="Raspbian - Update" caption="Raspbian - Update" %}

Na de update installeren we al de nieuwste versies van alle paketten aanwezig op het systeem (paketten worden niet verwijderd via het `upgrade` commando) door het volgende commando uit te voeren:

{% highlight bash %}
sudo apt-get upgrade -y
{% endhighlight %}

We kunnen ook gebruik maken van het commando [`dist-upgrade`](https://askubuntu.com/questions/194651/why-use-apt-get-upgrade-instead-of-apt-get-dist-upgrade) waarmee alle niet-gerelateerde paketten automatisch verwijderd worden. 

Herstart het systeem na `update` en `upgrade` via `sudo reboot`.

{% highlight bash %}
sudo reboot
{% endhighlight %}

Configuratie
------------

De `update` en `upgrade`-procedure kan een tijdje duren, zeker via Wifi. Na een **Coffee Break** kunnen we de noodzakelijke configuration van het Raspbian besturingssysteem aanpakken. Start de **Raspberry Pi Configuration** applicatie via de **Raspbian startknop &gt; Preferences &gt; Raspberry Pi Configuration**.

{% include shared/figure.html src="http://www.arteveldehogeschool.be/campusGDM/wanm/1718/syllabi/1718-wot/IMG_20170904_140728.jpg" alt="Raspbian - Configuratie" caption="Raspbian - Configuratie" %}

Via deze applicatie kunnen we het systeem (system), interfaces, performantie (performance) en localisatie (localisation) instellen. We **enable** voorlopig de interfaces: **Camera**, **SSH** en **Remote GPIO (general purpose input/output)**. Hierdoor kunnen we een aangesloten camera uitlezen, SSH-verbinding maken met de Raspberry PI en de [GPIO-aansluitingen](https://www.raspberrypi.org/documentation/usage/gpio/) van de Raspberry PI aanspreken en sturen.

{% include shared/figure.html src="http://www.arteveldehogeschool.be/campusGDM/wanm/1718/syllabi/1718-wot/IMG_20170904_140936.jpg" alt="Raspbian - Configuratie: Interfaces" caption="Raspbian - Configuratie: Interfaces" %}

### Localisation

Vervolgens stellen we de **Localisation** in, deze bestaat uit:

- Set Local  
Instellen van de taal (language), het land (country) en de karakterreeks (Character Set). De taal is `nl (Dutch)`, het land `BE (Belgium)` en de karakterreeks `UTF-8`. Uiteraard kies je voor de best passende instellingen die aanleunt bij je voorkeuren.
- Set Timezone  
Instellen van het gebied (area) en locatie (location). Het gebied is `Europe` en de locatie is `Brussels`.
- Set Keyboard  
Instellen van het land (country) en variant. Het land is `Belgium` en de variant `Belgian`.
- Set Wifi Country  
Instellen van het Wifi-land, in dit geval `BE Belgium`.

{% include shared/figure.html src="http://www.arteveldehogeschool.be/campusGDM/wanm/1718/syllabi/1718-wot/IMG_20170904_140952.jpg" alt="Raspbian - Configuratie: Localisation" caption="Raspbian - Configuratie: Localisation" %}

Na het instellen van de interfaces en de localisatie, kunnen we ook deze instellingen en bijkomende instellingen doen via het commando `sudo raspi-config` in CLI (Command Line Interface).

{% include shared/figure.html src="http://www.arteveldehogeschool.be/campusGDM/wanm/1718/syllabi/1718-wot/IMG_20170904_141413.jpg" alt="Raspbian - Update" caption="Raspbian - CLI: raspi-config" %}

In deze configuratie verander best het **paswoord** voor de Raspberry Pi alsook de **hostname**. Zorg ervoor dat de naam van jouw Raspberry Pi uniek is!

{% include shared/figure.html src="http://www.arteveldehogeschool.be/campusGDM/wanm/1718/syllabi/1718-wot/IMG_20170904_141439.jpg" alt="Raspbian - Update" caption="Raspbian - CLI: raspi-config" %}

> Links
> -----
> - <https://www.raspberrypi.org/documentation/configuration/raspi-config.md>
{:.card.card-definition}


### Datum en Tijd

We kunnen de datum en tijd instellen met en zonder het internet. Zonder het internet voeren we hetvolgende commando uit:

{% highlight bash %}
sudo date -s "Sat Sept 23 19:21:11 UTC 2017"
sudo dpkg-reconfigure tzdata
{% endhighlight %}

Of we kunnen, indien we internet hebben, gebruik maken van een **sntp**-server:

{% highlight bash %}
sudo sntp -s time.google.com
{% endhighlight %}

Python
------

{% highlight bash %}
sudo apt-get update
sudo apt-get install build-essential tk-dev libncurses5-dev libncursesw5-dev libreadline6-dev libdb5.3-dev libgdbm-dev libsqlite3-dev libssl-dev libbz2-dev libexpat1-dev liblzma-dev zlib1g-dev
{% endhighlight %}

{% highlight bash %}
wget https://www.python.org/ftp/python/3.6.0/Python-3.6.2.tar.xz
tar xf Python-3.6.2.tar.xz
cd Python-3.6.2
./configure
make
sudo make altinstall
python3.6 -m pip install --upgrade pip
{% endhighlight %}

{% highlight bash %}
sudo rm -r Python-3.6.2
rm Python-3.6.2.tgz
sudo apt-get --purge remove build-essential tk-dev
sudo apt-get --purge remove libncurses5-dev libncursesw5-dev libreadline6-dev
sudo apt-get --purge remove libdb5.3-dev libgdbm-dev libsqlite3-dev libssl-dev
sudo apt-get --purge remove libbz2-dev libexpat1-dev liblzma-dev zlib1g-dev
sudo apt-get autoremove
sudo apt-get clean
{% endhighlight %}

{% highlight bash %}
sudo python3.6 -m pip install --upgrade pip setuptools wheel
{% endhighlight %}

> Links
> -----
> - <https://tecadmin.net/install-python-3-6-ubuntu-linuxmint/#>
> - <https://gist.github.com/dschep/24aa61672a2092246eaca2824400d37f>
{:.card.card-definition}

git
---

`git` is standaard geïnstalleerd op Raspbian. De versie bedraag `v2.1.4`. Wanneer we `git` wensen up te daten via `apt-get`, dan zal de package manager de melding geven "git is reeds de nieuwste versie".

{% highlight bash %}
sudo apt-get install git
{% endhighlight %}

Willen we toch gebruik maken van de laatste git versie `v2.14`, dan moeten `git` zelf bouwen via de source. Dit is echter af te raden omdat deze versie niet uitgebreid getest is geweest door de community voor een specifiek besturingssysteem.

{% highlight bash %}
git clone https://github.com/git/git
cd git
{% endhighlight %}

Node.js
-------

Om Node.js op Raspberry Pi3 te installeren voeren we de volgende commando's uit:

{% highlight bash %}
wget https://nodejs.org/dist/v8.6.0/node-v8.6.0-linux-armv7l.tar.gz
tar -xvf node-v8.6.0-linux-armv7l.tar.gz
cd node-v8.6.0-linux-armv7l
sudo cp -R * /usr/local/
sudo reboot
{% endhighlight %}

Om de installatie te testen na reboot voeren we de volgende commando's uit:

{% highlight bash %}
node -v
npm -v
{% endhighlight %}

Deze commando's tonen de versie van respectievelijk de `node`- en `nmp`-cli. Op 03-10-2017 draagt `node` de versie `v8.6.0`.

nodeimu
-------

**Nodejs bindings** om toegang te hebben tot **IMU/pressure/humidity/temperature data** gebruik maken van de [RTIMULib2-bibliotheek](https://github.com/richards-tech/RTIMULib2.git). Deze bibliotheek gebruikt [nodejs/nan](https://github.com/nodejs/nan.git). Deze bibliotheek bevat **Native Abstractions** voor Nodejs. nodeimu is getest op de [Sense HAT](https://www.raspberrypi.org/products/sense-hat/) en op [GrovePi+](http://www.dexterindustries.com/grovepi/) voor de Raspberry Pi3.

{% highlight bash %}
git clone https://github.com/rupnikj/nodeimu --recursive && cd nodeimu
npm install node-gyp -g
npm install
{% endhighlight %}

GPIO via Node.js
----------------

### rpi-gpio

Spreek de Raspberry Pi GPIO pins aan m.b.v. **io.js / node.js**.

> Links
> -----
> - <https://www.npmjs.com/package/rpi-gpio>
{:.card.card-link}

### node-rpio

Raspberry Pi GPIO bibliotheek voor node.js.

> Links
> -----
> - <https://github.com/jperkin/node-rpio>
{:.card.card-link}

### onoff

GPIO toegang met Node.js.

> Links
> -----
> - <https://github.com/fivdi/onoff>
> - <https://webofthings.org/2016/10/23/node-gpio-and-the-raspberry-pi/>
> - <https://github.com/webofthings/wot-book>
{:.card.card-link}