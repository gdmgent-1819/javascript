---
layout: course
title: Windows
title_long: Dotfiles Windows
permalink: ontwikkelomgeving/dotfiles/win/
---
{% include abbreviations/cli.md %}
{% include abbreviations/education.md %}
{% include abbreviations/computer.md %}
{% include abbreviations/kbd.md %}
{% include hyperlinks/education.md %}
{% include hyperlinks/software.md %}

> Opmerking
> ---
> Deze installatie-instructies zijn bedoeld voor *&nbsp;*{:.fa.fa-fw.fa-windows}**Windows 10** (Versie 10.0.**15063**), maar werken waarschijnlijk ook voor andere versies van Windows.
{:.card.card-remark}

Benodigdheden
-------------

### Teksteditor

[*&nbsp;*{:.fa.fa-fw.fa-download}Visual Studio Code voor Windows](https://code.visualstudio.com/download){:.button.button--standard.button--primary}

Om te testen of de opdracht goed geïnstalleerd is, open je de **Opdrachtprompt** *(Command)* en vraag je de versie (`--version`) van Visual Studio Code (`code`) op. 

{% highlight cmd %}
C:> code --version
{% endhighlight %}

Nu kan je vanuit de **Opdrachtprompt** *(Command)* bestanden open met [Visual Studio Code][].

### PowerShell

Download de *installer* (`.msi`) onderaan de pagina:

[*&nbsp;*{:.fa.fa-fw.fa-download}PowerShell voor Windows][PowerShell]{:.button.button--standard.button--primary}

Na de installatie open je **PowerShell 6.0** als **Administrator**.

> Opmerking
> ---
> **PowerShell 6.0** is niet hetzelfde als **Windows PowerShell** of **Windows PowerShell ISE**!
{:.card.card-remark}

> Opgelet
> ---
> Open **PowerShell 6.0** ALTIJD als **Administrator**.
{:.card.card-warning}

### Git

Download en installeer:

[*&nbsp;*{:.fa.fa-fw.fa-git}Git][]{:.button.button--standard.button--primary}

Gebruik deze instellingen (laat de overige op de standaardinstellingen staan):

 - `Use Git and optional Unix tools from the Windows Command Prompt`
 - `Use the OpenSSL library`
 - `Checkout windows-style, commit Unix-style line endings`
 - `Use Windows' default console window`
 - `Enable files system caching`
 - `Enable Git Credential Manager`

Open **PowerShell 6.0** en voer `git --version` uit om te testen of Git geïnstalleerd is.

> Opgelet
> ---
> Onderstaande PowerShell-opdracht knip je met <kbd>Ctrl</kbd>+<kbd>C</kbd> en plak je met <kbd>RMK</kbd> <mark class="marker--underline marker--yellow">zonder <code>PS&gt; </code> </mark> in het PowerShell-venster.
{:.card.card-warning}

{% highlight posh %}
PS> git --version
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
PS> Set-ExecutionPolicy -ExecutionPolicy Unrestricted
PS> .\install.ps1
{% endhighlight %}

Open een nieuw **PowerShell 6.0**-venster en je zou `gdm.gent Dotfiles on PowerShell for Windows` te zien moeten krijgen, zonder rode foutmeldingen.
