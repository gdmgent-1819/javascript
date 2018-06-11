---
layout: course
title: macOS
title_long: Dotfiles macOS
permalink: ontwikkelomgeving/dotfiles/mac/
---
{% include abbreviations/cli.md %}
{% include abbreviations/education.md %}
{% include abbreviations/computer.md %}
{% include abbreviations/kbd.md %}
{% include hyperlinks/education.md %}
{% include hyperlinks/software.md %}

> Opmerking
> ---
> Deze installatie-instructies zijn bedoeld voor *&nbsp;*{:.fa.fa-fw.fa-apple}**macOS Sierra** (Versie 10.**12**), maar werken waarschijnlijk ook voor andere versies van macOS.
{:.card.card-remark}

Benodigdheden
-------------

### Teksteditor

[*&nbsp;*{:.fa.fa-fw.fa-download}Visual Studio Code voor macOS](https://code.visualstudio.com/download){:.button.button--standard.button--primary}

Om [Visual Studio Code][] vanuit de macOS **Terminal** te kunnen openen met de opdracht `code`, moeten we in de applicatie eenmalig een script uitvoeren.

> Visual Studio Code
> ---
> Start de applicatie en open de **Command Palette** met <kbd class="menu"><kbd>View</kbd>&#9656;<kbd>Command Palette...</kbd></kbd> of <kbd class="keyboard"><kbd>&#8679; Shift</kbd>+<kbd>Cmd</kbd>+<kbd>P</kbd></kbd>  
> en voer `Shell Command: Install 'code' command in PATH` uit.
{:.card.card-app}

Om te testen of de opdracht goed geïnstalleerd is, open je de **Terminal** en vraag je de versie (`--version`) van Visual Studio Code (`code`) op.

> Opgelet
> ---
> Onderstaande PowerShell-opdracht knip je met <kbd class="keyboard"><kbd>Cmd</kbd>+<kbd>C</kbd></kbd> en plak je met <kbd>RMK</kbd> <mark class="marker--underline marker--yellow">zonder <code>$ </code> </mark> in het Terminal-venster.
{:.card.card-warning}

{% highlight terminal %}
$ code --version
{% endhighlight %}

Nu kan je vanuit de **Terminal** bestanden open met [Visual Studio Code][].

### PowerShell

Download de *installer* (`.pkg`) onderaan de pagina:

[*&nbsp;*{:.fa.fa-fw.fa-download}PowerShell voor macOS][PowerShell]{:.button.button--standard.button--primary}

Na de installatie moeten we PowerShell nog instellen als de standaard Shell.

<kbd class="menu"><kbd>Terminal</kbd>&#9656;<kbd>Voorkeuren&hellip;</kbd>&#9656;<kbd>Algemeen</kbd></kbd> en verander:

 - Open shells met:
   - Commando (volledig pad): `/usr/local/bin/powershell -NoLogo`

Open een nieuw **Terminal**-venster en vraag de versie van PowerShell op.

> Opgelet
> ---
> Onderstaande PowerShell-opdracht knip je met <kbd class="keyboard"><kbd>Ctrl</kbd>+<kbd>C</kbd></kbd> en plak je met <kbd class="keyboard"><kbd>Cmd</kbd>+<kbd>V</kbd></kbd> <mark class="marker--underline marker--yellow">zonder <code>PS&gt; </code> </mark> in het PowerShell-venster.
{:.card.card-warning}

{% highlight posh %}
PS> $PSVersionTable.GitCommitId
{% endhighlight %}

### Command Line Developer Tools

Open **Terminal** en voer `git --version` uit om te testen of Git geïnstalleerd is.

{% highlight posh %}
PS> git --version
{% endhighlight %}

> Opmerking
> ---
> Indien [Git][] nog niet geïnstalleerd is, zal een popupvenster verschijnen.  
> Klik op de knop **Installeer** om de **Command Line Developer Tools** te installeren.
{:.card.card-remark}

Indien het popupvenster niet verschijnt, kan je het manueel starten met:

{% highlight posh %}
PS> xcode-select --install
{% endhighlight %}

Installatie
-----------

### Repository klonen

> Opgelet
> ---
> Zorg ervoor dat je op school via *&nbsp;*{:.fa.fa-fw.fa-wifi} Artevelde HS **Open** verbindt totdat de dotfiles geïnstalleerd zijn!
{:.card.card-warning}

Ga naar de Home-map en kloon de GitHub-repository.

{% highlight posh %}
PS> Set-Location -Path $Home
PS> git clone https://github.com/gdmgent/dotfiles/ --single-branch
{% endhighlight %}


### Profiel instellen

Ga naar de gekloonde Dotfiles-map en voer het installatiescript uit.

{% highlight posh %}
PS> Set-Location -Path dotfiles
PS> .\install.ps1
{% endhighlight %}

Open een nieuw **Terminal**-venster en je zou `gdm.gent Dotfiles on PowerShell for macOS` te zien moeten krijgen, zonder rode foutmeldingen.


Post-installatie
----------------

### Homebrew & Homebrew Cask

#### Homebrew

##### Homebrew is nog niet geïnstalleerd

[Homebrew][] is een *package manager* voor macOS. Packages worden **formulae** voor **brews** genoemd, en opgeslagen in een **cellar**.

Open **Terminal** en installeer Homebrew door het [Dotfiles][]-script uit te voeren.

{% highlight posh %}
PS> InstallBrew
{% endhighlight %}

{% highlight posh %}
PS> brew --version
{% endhighlight %}

Je kan eventuele problemen detecteren met de Homebrew-opdracht `doctor`. Volg indien nodig het advies.

{% highlight posh %}
PS> brew doctor
{% endhighlight %}

##### Homebrew is al geïnstalleerd

Als Homebrew al eerder geïnstalleerd werd, moet je deze stappen doorlopen:

| Stap | Opdracht       | Verklaring                                       |
|:----:|----------------|--------------------------------------------------|
|   1  | `brew update`  | Update naar de nieuwste versie van Homebrew.     |
|   2  | `brew upgrade` | Waardeer alle verouderde formulae op.            |
|   3  | `brew cleanup` | (Optioneel: verwijder alle verouderde formulae.) |
{:.table}

Door het [Dotfiles][]-script uit te voeren kan je de drie stappen in een keer uitvoeren.

{% highlight posh %}
PS> UpdateBrew
{% endhighlight %}

> Tip
> ---
> Verouderde formulae kunnen verwijderd worden met de Homebrew-opdracht `cleanup`. Soms is het echter beter om de oudere versies te bewaren zodat je die opnieuw kan installeren mochten er problemen zijn met nieuwe versies. Gebruik `brew switch` om vorige versies opnieuw te installeren.
{:.card.card-tip}

#### Homebrew Cask

[Homebrew Cask][Cask] is een **Homebrew**-uitbreiding om **Casks** (macOS-applicaties met een grafische interface) te installeren vanaf de Terminal.

{% highlight posh %}
PS> brew tap caskroom/cask
{% endhighlight %}

#### Git

Op macOS wordt [Git][] samen met de *Xcode Command Line Tools* geïnstalleerd. Het kan echter handig zijn om de allerlaatste versie te hebben. Deze versie kan je met Homebrew installeren.

{% highlight posh %}
PS> InstallGit
{% endhighlight %}

> Tip
> ---
> Je kan nagaan wat het pad is naar het uitvoerbaar bestand dat standaard aangeroepen wordt, door de opdracht `which` te gebruiken.
{:.card.card-tip}

{% highlight posh %}
PS> which git
{% endhighlight %}