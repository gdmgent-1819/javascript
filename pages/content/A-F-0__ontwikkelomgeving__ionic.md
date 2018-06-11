---
layout: course
title: Ionic
title_long: Ionic
permalink: ontwikkelomgeving/ionic/
---

Inleiding
---------

Ionic is een HTML5 SDK of framework waarmee we **Hybrid Modile Applications** kunnen ontwikkelen m.b.v. webtechnologieën zoals: HTML, CSS en JavaScript. Dit framework helpt om native-feeling apps te ontwikkelen, zonder dat we echt een Native programmeertaal moeten gebruiken zoals: Java, Objective-C, Swift, e.d. .

De focus van het Ionic-framework is op de look and feel en de UI-interactie. Dit betekent dat het frontend gedeelte van de toekomstige app wordt aangepakt door dit framework.

Ionic is gebaseerd op [Angular](https://angular.io/)-framework en uitgebreid met functionaliteit (Cordova / PhoneGap) om een webapp te converteren (porten) naar een native app. Vandaar de naam Hybrid-app.

Installatie
-----------

[Ionic CLI](https://ionicframework.com/docs/cli/) is het command line tool op Ionic-apps te ontwikkelen. Om de laatste distributie van Ionic CLI te ontavngen hebben [Node 6+](https://nodejs.org/en/download/) en [NPM 3+](https://www.npmjs.com/) nodig. Node brengt o.a. JavaScript naar de server. NPM is een **package manager** voor **JavaScript**. Node (en dus ook NPM, omdat dit een onderdeel is van Node.js) kan eenvoudig geïnstalleerd worden via de [Dotfiles](../dotfiles/).

Node zullen installeren via Node Version Manager (NVM). NVM beheert verschillende actieve Node.js versies op het besturingssysteem.

{% highlight posh %}
InstallNvm
{% endhighlight %}

We voeren het volgende commando uit om de laatste Node.js versie te installeren.

{% highlight posh %}
InstallNode
{% endhighlight %}

Om de laatste Node.js versie te gebruiken voeren we het volgende commando uit:

{% highlight posh %}
UseNode8
{% endhighlight %}

Na de installatie van deze Noodzakelijke dependencies kunnen we de Ionic-cli installeren via Yarn:

{% highlight bash %}
yarn global add ionic@latest
yarn global add cordova
yarn global add typescript
{% endhighlight %}

Of via één commandoregel:

{% highlight zsh %}
yarn global add ionic@latest cordova typescript
{% endhighlight %}

Installatie van een [plugin](https://www.npmjs.com/package/@ionic/cli-plugin-proxy) voor ionic-cli om te werken achter een proxy-server is noodzakelijk. Installatie van de plugin via:

{% highlight zsh %}
yarn global add @ionic/cli-plugin-proxy
{% endhighlight %}

