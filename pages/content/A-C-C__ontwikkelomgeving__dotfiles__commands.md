---
layout: course
title: Commando's
title_long: Dotfiles commando's
permalink: ontwikkelomgeving/dotfiles/commands
---
{% include abbreviations/cli.md %}
{% include abbreviations/education.md %}
{% include abbreviations/computer.md %}
{% include abbreviations/kbd.md %}
{% include hyperlinks/csse.md %}
{% include hyperlinks/education.md %}
{% include hyperlinks/software.md %}

Proxy
-----

### Wanneer de proxyserverinstellingen gebruiken?

> Proxy wel gebruiken
> ---
> *&nbsp;*{:.fa.fa-fw.fa-wifi} Artevelde HS **Veilig**  
> *&nbsp;*{:.fa.fa-fw.fa-sitemap} Artevelde HS **Ethernet**
{:.card.card-thumbs-up}

> Proxy niet gebruiken
> ---
> *&nbsp;*{:.fa.fa-fw.fa-wifi} Artevelde HS **Open**  
> *&nbsp;*{:.fa.fa-fw.fa-wifi} Wifi **Thuis**  
> *&nbsp;*{:.fa.fa-fw.fa-sitemap} Ethernet **Thuis**
{:.card.card-thumbs-down}

### Handmatig macOS

Je kan de proxyserverinstellingen handmatig invoeren.

De proxyserverinstellingen invoeren voor de rest van de sessie.

{% highlight terminal %}
$ PXY=http://proxy.arteveldehs.be:8080 && NOPXY=localhost,127.0.0.1,.local && export HTTP_PROXY=$PXY HTTPS_PROXY=$PXY FTP_PROXY=$PXY NO_PROXY=$NOPXY http_proxy=$PXY https_proxy=$PXY ftp_proxy=$PXY no_proxy=$NOPXY && unset PXY NOPXY
{% endhighlight %}

De proxyserverinstellingen ongedaan maken met de opdracht `unset`, of sluit gewoon het Terminal-venster en open een nieuw.

{% highlight terminal %}
$ unset HTTP_PROXY HTTPS_PROXY FTP_PROXY NO_PROXY http_proxy https_proxy ftp_proxy no_proxy
{% endhighlight %}

### Handmatig Windows

Je kan de proxyserverinstellingen handmatig invoeren.s

> Windows
> ---
> Open de gebruikersvariabelen.  
> <kbd class="menu"><kbd>Omgevingsvariabelen…</kbd>&#9656;<kbd>Gebruikersvariabelen</kbd></kbd>
{:.card.card-windows}

| Variable      | Waarde                             |
|:--------------|:-----------------------------------|
| `HTTP_PROXY`  | `http://proxy.arteveldehs.be:8080` |
| `HTTPS_PROXY` | `http://proxy.arteveldehs.be:8080` |
| `FTP_PROXY`   | `http://proxy.arteveldehs.be:8080` |
| `NO_PROXY`    | `localhost,127.0.0.1,.local`       |
{:.table}

> Tip
> ---
> Om de proxyserverinstellingen tijdelijk uit te schakelen kan je de naam van de variabelen wijzigen.
> Zet er bijvoorbeeld een `!` voor.
{:.card.card-tip}

### De beste optie via Powershell-script

{% highlight posh %}
PS> proxy
{% endhighlight %}

{% highlight posh %}
PS> proxy on
{% endhighlight %}

{% highlight posh %}
PS> proxy off
{% endhighlight %}


Node Version Manager Installeren
--------------------------------

{% highlight posh %}
PS> InstallNvm
{% endhighlight %}

Node 8 Installeren
------------------

Open Powershell 6 Opnieuw.

{% highlight posh %}
PS> InstallNode
PS> UseNode8
{% endhighlight %}

Yarn Installeren
----------------

[Yarn][] is een alternatief voor het standaard met [Node.js][] meegeleverde **npm**.

{% highlight posh %}
PS> InstallYarn
{% endhighlight %}

Mappen
------

### Home-map

{% highlight posh %}
PS> ~
{% endhighlight %}

### Code-map

{% highlight posh %}
PS> c
{% endhighlight %}

Je kan rechtstreeks naar de submappen in de Code-map gaan. Met <kbd>Tab</kbd> kan je de submappen automatisch laten aanvullen.

{% highlight posh %}
PS> c code-webtech1
{% endhighlight %}

### Syllabi-map

{% highlight posh %}
PS> s
{% endhighlight %}

{% highlight posh %}
PS> s 1718-ehbi
{% endhighlight %}


