---
layout: course
title: Git
title_long: Git
permalink: ontwikkelomgeving/git/
---

Inleiding
---------

> Git
> ---
> **Git** staat voor **"Global Information Tracker"**. Het is een revisie (revision control) beheersysteem en een broncode (source code) management systeem (SCM) vergelijkbaar met het alomgekende **SVN**-systeem (2001 e.v.). 
{:.card.card-definition}

Het Git-systeem, initieel ontwikkeld door Linus Torvalds voor de Linux Kernel Development in 2005, voldoet aan een aantal vereisten (requirements):

- gratis;
- eenvoudig, snel en efficiënt;
- betrouwbaar;
- schaalbaar (scalable)  
  Met honderden teamleden kunnen samenwerken aan hetzelfde project.
- geschiedenis  
  Weten wie wat gedaan heeft en wanneer?
- transacties;
  Meerdere acties bundelen.
- ondersteuning voor branches  
  Afsplitsing van het hoofdproject die later terug kan samengevoegd worden met het hoofdproject.
- ...

Iedere Git-werkmap bevat een volledige **repository** met een overzicht van de geschiedenis en bevat ook **tracking capaciteiten**. Git is niet afhankelijk van een centrale opslagplaats! 

Nieuwe versies van een app worden eerst **lokaal bewaard** in een **lokale copy van de centrale opslagplaats** (server). Deze lokale opslagplaats kan later **gesynchroniseerd** worden met de centrale opslagplaats. **Conflicten** in versies worden aangeduid door de Git-software, zodat een teamlid deze kan oplossen!

Installatie via Dotfiles
------------------------

Deze installatiemethode geniet de voorkeur! Volg de volgende [installatieprocedure macOS](../dotfiles/mac/#git) of [installatieprocedure Windows](../dotfiles/win/#git).

Installatie via executables
---------------------------

### macOS

Open **Terminal** en voer `git --version` uit om te testen of git geïnstalleerd is.

{% highlight bash %}
git --version
{% endhighlight %}

> Opmerking
> ---
> Indien Git nog niet geïnstalleerd is, zal een popupvenster verschijnen.
> Klik op de knop "**Installeer**" om de **Command Line Developer Tools** te installeren.
{:.card.card-definition}

Indien het popupvenster niet verschijnt, kan je het manueel starten met:

{% highlight bash %}
xcode-select --install
{% endhighlight %}

### Windows

> Download
> --------
> <http://msysgit.github.io/>
{:.card.card-definition}

Vergeet niet de laatste of voorlaatste optie te selecteren tijdens de "Git Setup Installatie Wizard". Op deze manier kunnen we het git commando overal aanspreken (Het pad naar de Git executable wordt aan de systeemvariabelen toegevoegd)!

Installatie via package managers
--------------------------------

### macOS

Git kan op macOS ook geïnstalleerd worden via Homebrew:

{% highlight bash %}
brew install git
{% endhighlight %}

Het is aan te raden om bij de installatie van git via Homebrew de commando's `brew update`, `brew doctor` en `brew upgrade` uit te voeren.

### Windows

Git kan op Windows ook geïnstalleerd worden via [Chocolatey](https://chocolatey.org/packages/git.install):

{% highlight cmd %}
choco install git.install
{% endhighlight %}

Om git the upgraden via Chocolatey:

{% highlight cmd %}
choco upgrade git.install
{% endhighlight %}

Het is aan te raden om bij de installatie van git of andere tools, Chocolatey te [upgraden](https://github.com/chocolatey/choco/wiki/CommandsUpgrade) via het commando `choco upgrade chocolatey`.

Commando's
----------

- Installatie nakijken door `git` uit te voeren in de Commandline;
- Ophalen van het versienummer van `git`.
	- `git --version` 
- Toevoegen van bestanden en mappen aan de volgende commit.
	- `git add *.*` of `git add .`
- Commit of doorvoeren van de toegevoegde bestanden en mappen.
	- `git commit -m "Update Git Repository"`
- Push of versturen van de commit naar de online repository.
	- `git push -u origin master`

Configuratie
------------

### Identiteit

Het eerste dat we moeten doen nadat we Git hebben geïnstalleerd is om onze gebruikersnaam en e-mailadres in te stellen. Dit is belangrijk omdat elk **Git commit** commando deze informatie gebruikt om het commit object te ondertekenen. Deze informatie zit vervat als meta-informatie in een commit beschrijving.

{% highlight bash %}
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
{% endhighlight %}

Bijvoorbeeld:

{% highlight bash %}
git config --global user.name "drdynscript"
git config --global user.email "philippe.depauw@arteveldehs.be"
{% endhighlight %}

Dit hoeft enkel maar **eenmaal** uitgevoerd te worden omdat we de `--global` optie vermelden. Git zal steeds deze instellingen gebruiker voor alles wat je gerelateerd doet op het systeem. Indien we deze instellingen willen overschrijven voor een project, dan voeren we deze commando's uit zonder de `--global` optie.

### Forceren van `https` i.p.v. `git`

Binnen het netwerk van de Arteveldehogeschool wordt het `git-protocol` geblokkeerd door de firewall. We kunnen dit protocol vervangen door `https`via de volgende configuratie:

{% highlight bash %}
git config --global url."https://".insteadOf git://
{% endhighlight %}

Op deze manier gebruiken we altijd `https`-protocol i.p.v. `git`-protocol. De overdracht van data zal dus voortaan geschieden via `https`.

### Editor

Now that your identity is set up, you can configure the default text editor that will be used when Git needs you to type in a message. By default, Git uses your system’s default editor, which is generally Vi or Vim. If you want to use a different text editor, such as Emacs, you can do the following:

Via configuratie kunnen we de standaard editor instellen, die Git zal gebruiken wanneer we een boodschap (message) moeten typen. Standaard wordt de "default" editor van het besturingssysteem gebruikt: notepad (Windows), vi of vim (macOS), ... .

{% highlight bash %}
git config --global core.editor emacs
{% endhighlight %}

VS Code kunnen we instellen als default editor:

{% highlight bash %}
git config --global core.editor "code --wait"
{% endhighlight %}

### Merge en Diff tool

Specifiëren van de standaard "merge tool" om "merge conflicts" op te lossen.

Another useful option you may want to configure is the default diff tool to use to resolve merge conflicts. Say you want to use vimdiff:

vimdiff instellen als standaard "merge tool":

{% highlight bash %}
git config --global merge.tool vimdiff
git config --global diff.external vimdiff
{% endhighlight %}

VS Code kunnen we instellen als default "merge tool":

{% highlight bash %}
git config --global merge.tool vscodemerge
git config --global mergetool.vscodemerge.cmd 'code --wait --diff $LOCAL $REMOTE'
git config --global mergetool.vscodemerge.trustExitCode false
git config --global diff.external code
{% endhighlight %}

### Commit template

If you set this to the path of a file on your system, Git will use that file as the default message when you commit. For instance, suppose you create a template file at $HOME/.gitmessage.txt that looks like this:

Een commit template is een template dat door Git wordt gebruikt als standaardbericht voor een "commit". Deze template wordt gedefinieerd in een tekstbestand `.gitmessage.txt` meestal onder de home-directory.

Voorbeeld inhoud `.gitmessage.txt`bestand:

{% highlight txt %}
-> Subject

-> What have you done?

New Media Development | Graphical and Digitale Media | Artevelde University College Ghent
{% endhighlight %}

Instellen van deze template voor git commits:

{% highlight bash %}
git config --global commit.template $HOME/.gitmessage.txt
{% endhighlight %}

### Proxy-server

Binnen het netwerk van de Arteveldehogeschool zijn, zoals gekend, drie soorten netwerken beschikbaar. Connecteren we via **AHS-veilig** of via de **Ethernet-kabel**, dan moeten we de proxy-server instellen. Voor het netwerk **AHS-open** hoeven deze instellingen **niet** te gebeuren. Indien de globale proxy-instellingen niet zijn ingesteld, dan kunnen we deze instellen enkel voor Git. Dat doen we door de volgende commando's uit te voeren:

{% highlight bash %}
git config --global http.proxy "http://proxy.arteveldehs.be:8080"
git config --global https.proxy "http://proxy.arteveldehs.be:8080"
{% endhighlight %}

We kunnen ook globale proxy-instellingen gebruiken voor heel het OS, zie: [Proxyserver instellingen](../../netwerk/proxy).

Werken we op een andere locatie, buiten het netwerk van de Arteveldehogeschool, is de kans groot dat er geen proxy-server aanwezig is waardoor we deze instellingen moeten verwijderen uit het Git configuratiebestand.  Dat doen we door de volgende commando's uit te voeren:

{% highlight bash %}
git config --global --unset http.proxy
git config --global --unset https.proxy
{% endhighlight %}

- Username
	- `git config --global user.name "drdynscript"`
- Email = Account
	- `git config --global user.email "drdynscript@gmail.com"`
- Proxy servers (ArteveldeHS Veilig of Ethernet-kabel)
	- `git config --global http.proxy "http://proxy.arteveldehs.be:8080"`
	- `git config --global https.proxy "http://proxy.arteveldehs.be:8080"` 
- Verwijderen van Proxy servers
	- `git config --global --unset http.proxy`
	- `git config --global --unset https.proxy`
- Https gebruiken i.p.v. git (proxy)
	- `git config --global url."https://github.com".insteadOf git://github.com`
- Editeren van `.gitconfig`
	- **macOS:** `vi ~/.gitconfig` of `grep ~/.gitconfig` (vi & grep zijn editors)
	- **Windows via Microsoft Visual Code:** `code %HOMEPATH%/.gitconfig`

Door één van deze handelingen uit te voeren wordt er een configuratiebestand geschreven op de locatie `~/.gitconfig` (of `~/.config/git/config`). `~` komt overeen met de home-locatie van een gebruiker, bv. op Windows: `C:\Users\drdynscript`.

.gitignore
----------

Via een `.gitignore` bestand in de root van een Git-enabled project vermelden we de folders en/of bestanden die we niet in de online repository willen overbrengen. Courante onderdelen binnen dit bestand zijn goed samengevat in deze [Gist .gitignore](https://gist.github.com/octocat/9257657).

Het `.gitignore` bestand bevat meestal regels voor IDE's, zoals JetBrains, Miscrosoft Visual Code, Dreamweaver, ... . Daarnaast moet gecompileerde code, zoals exe, com, rar, ... vermeld worden. Packages, logs, cache, tijdelijke folders, ... maken ook deel uit van het `.gitignore` bestand. Het onderstaande bestand geeft een goede indicatie van een courant `.gitignore` bestand. Via [gitignore.io](https://www.gitignore.io/) kunnen we zo'n bestand genereren.

Naast dit lokaal bestand kunnen we ook een globaal `.gitignore` bestand aanmaken. Onder de **Home** folder (`~/.gitignore_global`) van de gebruiker maken we het bestand `.gitignore_global` aan waarin we de algement globale .gitignore zullen toevoegen. Op deze manier hoeven we enkel in het lokaal bestand applicatiespecifieke instellingen toe te voegen.
  
Opdat deze globale instellingen van kracht worden moeten we dit `.gitignore_global` bestand toevoegen aan de Git configuratie:

{% highlight zsh %}
git config --global core.excludesfile ~/.gitignore_global
{% endhighlight %}

Meer informatie over dit `.gitignore_global` bestand via de [dotfiles](http://www.gdm.gent/dotfiles/global-gitignore/).

README.md
--------- 

Op GitHub, GitLab en BitBucket staat dit `README.md` bestand o.a. in de hoofdfolder (top-level directory). Dit bestand, met de markdown syntax, wordt automatisch geconverteerd naar HTML. Het wordt gepresenteerd wanneer we de Git repository bezoeken. Het `README.md` bestand bevat meestal informatie over andere bestanden, folders of archieven binnen dezelfde repository. De naam wordt meestal beschreven in capitalen (uppercase), behalve de extensie.

Het `README.md` bestand bevat meestal één of meerdere onderwerpen als inhoud:

* Omschrijving van de repository (project);
* Oplijsting van aanwezige bestanden en folders;
* Configuratie en installatie instructies;
* Documentatie;
* Gekende bugs;
* Aanvragen voor toekomstige nieuwe features;
* Auteurs;
* Copyright en licentie.