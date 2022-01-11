---
title: Info
layout: page
permalink: /info
---

{%- assign utils = false -%}
{%- assign lootboxes = false -%}
{%- assign puppeteer = false -%}
{%- for mod in site.data.modlist -%}
    {%- case mod.name -%}
        {%- when 'ToolkitUtils' %}
            {%- assign utils = true -%}
        {%- when 'ToolkitUtils - Testing' -%}
            {%- assign utils = true -%}
        {%- when 'Puppeteer' -%}
            {%- assign puppeteer = true -%}
        {%- when 'TwitchToolkit - Lootboxes' -%}
            {%- assign lootboxes = true -%}
    {%- endcase -%}
{%- endfor -%}


{%- assign bal = '!bal' -%}
{%- assign buy = '!buy' -%}
{%- for command in site.data.commands -%}
    {%- if command.data.isBal -%}
        {%- assign bal = command.usage -%}
        {%- continue -%}
    {%- endif -%}

    {%- if command.data.isBuy -%}
        {%- assign buy = command.usage -%}
        {%- continue -%}
    {%- endif -%}
{%- endfor -%}

# Welcome

Bienvenido a [{{ site.data.social.twitch }}](https://twitch.tv/{{ site.data.social.twitch }}) stream.
El stream usa este mod
[Twitch Toolkit](https://steamcommunity.com/sharedfiles/filedetails/?id=1718525787) para proporcionar un
experiencia interactiva. Hay muchas cosas en el mod que pueden parecer complicadas incluso para los más experimentados.
usuarios, pero esta breve guía le ayudará a familiarizarse con las cosas.

## Que es Twitch Toolkit?

Twitch Toolkit es un mod de hodlhodl que permite a los espectadores afectar el juego de varias maneras. 
La más destacada es su [store]({{- "/" | relative_url -}}), que le permite comprar una serie de
cosas que el streamer seleccionó. Dependiendo de la compra, estas cosas aparecen en el juego o afectan el
juego de alguna manera. Otra forma en que los espectadores pueden interactuar con el juego es a través de las encuestas del mod.
Las opciones en estas encuestas dependen en gran medida de lo que esté habilitado en el mod.

## Que son los Coins?

Las monedas son la moneda del mod. Puede ver su saldo utilizando el comando `{{ bal }}`. 

{% if utils == true %}
Notarás que el comando de equilibrio puede tener algunos emojis nuevos. Si ese es el caso, aquí hay una descripción general
de los emojis de la siguiente manera:

- 💰 representa el numero de coins que tienes.
- ⚖ representa tu karma.
- 📈 representa la cantidad de monedas que ganas cada vez que el mod otorga monedas.
- 📉 representa la cantidad de monedas que pierdes cada vez que el mod quita monedas.

{% endif %}


{%- if lootboxes == true -%}
You'll also notice that you'll get a message from the bot about a lootbox. You can open this lootbox
by using the `!openlootbox` command, as well as check the number of lootboxes you have with `!lootboxes`.
You'll always get a new lootbox everyday.
{%- endif -%}


<br/>
## Que es el karma?
Karma es un sistema en el mod que intenta limitar la cantidad de eventos negativos que un espectador puede comprar en
una vez. Este sistema funciona modificando directamente la cantidad de monedas que los espectadores obtienen cada vez que el mod otorga monedas.
Esto significa que cuanto menor sea su karma, menor será su ganancia de monedas. El objetivo es que
los eventos negativos se esparzan más para que la colonia pueda recuperarse.

## ¿Cómo uso el kit de herramientas de Twitch??

Puede usar Twitch Toolkit de varias maneras: la forma más destacada es a través de su
[commands]({{- "/commands" | relative_url -}}). El comando más importante es `{{- buy -}}`
, que es el punto de entrada de mods para comprar cosas de la tienda. Otros comandos notables
son los comandos `!mypawn`, que le permiten ver información diversa sobre su personaje. No cubriremos
todos los comandos aquí, pero la mayoría de los comandos generalmente deben ser autodescriptivos o tener una descripción de
lo que hacen en la [commands]({{- "/commands" | relative_url -}}) pagina.


{%- if puppeteer -%}
<br/>
## What is Puppeteer?

[Puppeteer](https://steamcommunity.com/sharedfiles/filedetails/?id=2057192142) is a mod by Brrainz that
allows viewers to directly control their pawns, and even view a number of information about your pawn in
a graphical way. It also redirects some of the responses from Twitch Toolkit to its website to clean up
chat a bit. So, if you're logged into Puppeeter and you're wondering why the bot isn't responding to you,
you should check the `TT` tab on the website first.
{%- endif -%}
