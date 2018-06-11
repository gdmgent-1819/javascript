---
layout: course
title: VS Code
title_long: Microsoft Visual Studio Code
permalink: ontwikkelomgeving/vscode/
---

Inleiding
---------

> Microsoft Visual Studio Code
> ----------------------------
> Is klein en licht, maar bevat een sterke source code editor die draait op je desktop en is beschikbaar voor Windows, Mac en Linux. Het bevat ondersteuning voor JavaScript, TypeScript en Node.js en heeft een rijk ecosystem van extensies voor andere talen, zoals C++, C#, Python, PHP, Go, … .
{:.card.card-definition}

Voorlopig worden reeds meer dan 30 programmeertalen ondersteund, zoals: JavaScript, C#, C++, PHP, Java, HTML, CSS, SQL, … . Het editeren is gefocused op het schrijven van code (multiple cursors, autosave, …). Deze editor bevat verschillende features:

- snel zoeken via RegEX;
- definities van klassen e.d. bekijken;
- code outline;
- intellisense;
- debugging;
- git version control;
- vorm aanpasbaar door de gebruiker;
- uitbreidbaar via extensions;
- ... .

> **Links**
> ---------
>
> - [Intoductie video's](https://code.visualstudio.com/docs/introvideos/overview) Microsoft Visual Code
> - [Keyboard shortcuts](https://code.visualstudio.com/docs/customization/keybindings#_keyboard-shortcuts-reference)
{:.card.card-tip}

Installatie via Executables
---------------------------

Op 12-09-2017 bedraagt de laatste versienummer **1.16**.

### Op Windows

Download de **64-bit** versie om Microsoft Visual Studio Code ten volle te gebruiken!

Download via: <https://code.visualstudio.com/docs/?dv=win>

### Op macOS

1. Download via: <https://code.visualstudio.com/docs/?dv=osx>;
1. Dubbel-klik op het gedownloade arhiveerbestand om te inhoud uit te pakken;
1. Sleep de `Visual Studio Code.app` naar de Applicatiefolder (Applications folder), zodat deze beschikbaar is in het Launchpad.
1. Voeg VS Code toe aan de Dock door rechts te klinnen op het icoon en vervolgens te kiezen voor **Options, Keep in Dock**.

Command Line
------------

We kunnen VS Code ook uitvoeren via de terminal door het commando `code` te typen, nadat we dit commando toegevoegd hebben aan de `$PATH` waarde uit het systeem. Om dit te verwezenlijken lanceren we VS Code, vervolgens openen we het **Command Palette** via ⇧⌘P (macOS) of Cntrl+P (Windows) en typen hier `> shell command` om het commando `Shell Command: Install 'code'`. Herstart de terminal zodat de nieuwe waarde voor `$PATH` van kracht is.

Extensies
---------

> Extension Marketplace
> ---------------------
> - <https://code.visualstudio.com/docs/editor/extension-gallery>
> - <https://marketplace.visualstudio.com/vscode>
{:.card.card-definition}

Installatie van een aantal belangrijke extensies (via `⌘+P` of `Cntrl+P`):

- [Git Extension Pack](https://marketplace.visualstudio.com/items?itemName=donjayamanne.git-extension-pack)
- [Ionic Extension Pack](https://marketplace.visualstudio.com/items?itemName=loiane.ionic-extension-pack)
- [One Dark Pro](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme)  
  `ext install Material-theme` 
- [Typescript Hero](https://marketplace.visualstudio.com/items?itemName=rbbit.typescript-hero)
- [vscode-icons](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons)  
  `ext install vscode-icons`
- [VSCode for Node.js Development Pack](https://marketplace.visualstudio.com/items?itemName=nodesource.vscode-for-node-js-development-pack)