---
layout: course
title: OS
title_long: Operating System
permalink: ontwikkelomgeving/os/
---

Inleiding
---------

Het besturingssysteem is de belangrijkste software van je computer. Het is daarom belangrijk om het up-to-date te houden, te beveiligen en de bestanden regelmatig te backuppen.

Voor de start van het academiejaar doe je best een *clean install* van de laatste officiële versie zodat eventuele schadelijke of nutteloze software en bestanden verwijderd zijn.

Sluit je computer regelmatig af. Zo worden ook op hol geslagen processen afgesloten. Applicaties die de computer heel zwaar belasten kunnen de computer fysiek beschadigen.

macOS
-----

### Updaten

Update het macOS systeem naar de laatste versie (op 01-08-2017 [macOS Sierra 10.12.6](https://support.apple.com/nl-nl/HT207835)). Deze verbetert de stabiliteit en beveiliging van je computer. Om je computer te updaten ga je naar het `apple logo`, vervolgens selecteer je de optie `Over deze MAC`. In het geopende venster klik je op de `knop Software-update`. Installeer vervolgens de macOS Sierra-update. Je kan ook rechtstreeks naar de App Store app gaan en vervolgens klikken op de update knop. Je MAC moet wel herstart worden tijdens de installatie.

### Xcode

[Xcode](https://developer.apple.com/xcode/) is een IDE voor macOS en bevat tools om software te ontwikkelen voor macOS, iOS, watchOS, tvOS, .NET Core, ... . Een update naar de laatste versie is handig om eventuele conflicten te vermijden. Op 01-08-2017 is de versie 8.3.3 beschikbaar op je macOS. Gelieve deze update te installeren via de App Store.

### Homebrew

Homebrew is de ontbrekende **package manager** voor macOS. Homebrew installeert onderdelen die je nodig hebt tijdens development die Apple niet voorziet.

Installatie via `ruby`:

{% highlight bash %}
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
{% endhighlight %}

Het is af en toe noodzakelijk om de volgende brew commando’s uit te voeren:

- `brew update`  
Updaten van Homebrew naar de laatste versie;
- `brew doctor`  
Oplossen van issues o.a. verloren links;
- `brew upgrade`  
Upgraden van alle Homebrew paketten.

### Anti-virus

[Sophos Home](https://home.sophos.com/) beschermd elke Mac en PC van malware, viruses, ransomware, en ongepaste websites. Het gebruikt dezelfde technologieën die worden gebruikt in grote bedrijven om hun ondernemingen te beschermen.

### Anti-malware

Om het OS te vrijwaren van adware, spyware, dialers, rootkits, keyloggers, trojans, scumware, malware, toolbars en andere rotzooi is het raadzaam om naast een anti-virus programma ook een anti-spyware, anti-malware en anti-rootkits programma te installeren. Dat kan bijvoorbeeld met de programma's Windows Defender, Comodo Internet Security en/of Malwarebytes. Omdat de resultaten per tool kunnen verschillen, is het verstandig het systeem met meerdere tools te scannen.

Gebruik altijd de **laatste versie van de scansoftware en update de malware-definities** voordat een scan wordt uitgevoerd. Zorg er ook voor dat alle andere beveiligingsmaatregelen up-to-date blijven (download zo snel mogelijk de laatste virusdefinities en installeer nieuwe updates voor Windows en andere software), anders bestaat het risico dat de computer opnieuw besmet raakt!

> Tip
> ---
> Met het gebruik van systeemback-ups maakt dit soort software eigenlijk overbodig. Na het terugzetten van een (schone) systeemback-up bij een vermoedelijke besmetting is de PC altijd weer virus- en malwarevrij.
{:.card.card-tip}

De tool [Malwarebytes Free](https://nl.malwarebytes.com/mac/) controleert het systeem eenvoudig en snel op de aanwezigheid van kwaadwillende software, eventuele besmettingen kunnen direct worden verwijderd. In eerste instantie wordt een probeerversie van het premiumpakket geïnstalleerd, welke na 14 dagen automatisch wordt teruggezet naar de gratis basisversie (een uitgeklede versie waarbij de realtime beveiliging en enkele andere beschermingen komen te vervallen). Geen probleem, want ook zonder deze extra beveiligingen kan MalwareBytes nog steeds malware, spyware en rootkits opsporen en verwijderen.

Windows
-------

### Updaten

**Windows Update** kan volledig in de achtergrond werken. De update heeft enkel attentie nodig wanneer we de computer moeten herstarten. Om de noodzakelijke updates te bekijken navigeren we naar de `Settings (Windows key + I) > Update & Security > Windows Update`. Klik op de `link Check for updates` om de beschikbare updates te bekijken.

Onder de `Advanced options link` kunnen we o.a. instellen hoe updates geïnstalleerd zullen worden. We hebben een voorkeur voor de instelling: `Notify to schedule restart`.

### Anti-virus

[Sophos Home](https://home.sophos.com/) beschermd elke Mac en PC van malware, viruses, ransomware, en ongepaste websites. Het gebruikt dezelfde technologieën die worden gebruikt in grote bedrijven om hun ondernemingen te beschermen.

### Anti-malware

Om het OS te vrijwaren van adware, spyware, dialers, rootkits, keyloggers, trojans, scumware, malware, toolbars en andere rotzooi is het raadzaam om naast een anti-virus programma ook een anti-spyware, anti-malware en anti-rootkits programma te installeren. Dat kan bijvoorbeeld met de programma's Windows Defender, Comodo Internet Security en/of Malwarebytes. Omdat de resultaten per tool kunnen verschillen, is het verstandig het systeem met meerdere tools te scannen.

[Windows Defender](https://www.microsoft.com/en-us/windows/windows-defender) wordt uitgeschakeld indien andere beveilingssoftware geïnstalleerd is. en is ook niet meer op te starten (dit wordt automatisch hersteld door de beveiligingssoftware weer te verwijderen).

Gebruik altijd de **laatste versie van de scansoftware en update de malware-definities** voordat een scan wordt uitgevoerd. Zorg er ook voor dat alle andere beveiligingsmaatregelen up-to-date blijven (download zo snel mogelijk de laatste virusdefinities en installeer nieuwe updates voor Windows en andere software), anders bestaat het risico dat de computer opnieuw besmet raakt!

> Tip
> ---
> Met het gebruik van systeemback-ups maakt dit soort software eigenlijk overbodig. Na het terugzetten van een (schone) systeemback-up bij een vermoedelijke besmetting is de PC altijd weer virus- en malwarevrij.
{:.card.card-tip}

De tool [Malwarebytes Free](http://www.malwarebytes.org/antimalware/) controleert het systeem eenvoudig en snel op de aanwezigheid van kwaadwillende software, eventuele besmettingen kunnen direct worden verwijderd. In eerste instantie wordt een probeerversie van het premiumpakket geïnstalleerd, welke na 14 dagen automatisch wordt teruggezet naar de gratis basisversie (een uitgeklede versie waarbij de realtime beveiliging en enkele andere beschermingen komen te vervallen). Geen probleem, want ook zonder deze extra beveiligingen kan MalwareBytes nog steeds malware, spyware en rootkits opsporen en verwijderen.

### Chocolatey

[Chocolatey](https://chocolatey.org/) is de package manager voor Windows. Het een **decentralized framework** om applicaties en tools te installeren. Het is gebouwd bovenop de **NuGet** infrastructuur en gebruikt **Powershell** om pakketten te downloaden. Te volgen [installatieinstructies](https://chocolatey.org/install).

Installatie via `cmd`:

{% highlight cmd %}
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
{% endhighlight %}

of via `ps`(powershell):

{% highlight posh %}
iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
{% endhighlight %}

Upgrade chocolatey:

{% highlight cmd %}
choco upgrade chocolatey
{% endhighlight %}