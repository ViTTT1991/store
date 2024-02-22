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

Добро пожаловать на стрим [{{ site.data.social.twitch }}](https://twitch.tv/{{ site.data.social.twitch }}).
На этом стриме используется мод
[Twitch Toolkit](https://steamcommunity.com/sharedfiles/filedetails/?id=1718525787) для обеспечения интерактивности. В моде есть многое, что может показаться сложным даже более опытным пользователям, но это краткое руководство поможет вам освоиться.

## Что такое Twitch Toolkit?

Twitch Toolkit — это мод от hodlhodl, который позволяет зрителям влиять на игру разными способами. Самым известным из них является [store]({{- "/" | relative_url -}}), в котором можно приобрести ряд вещей, созданных стримером. В зависимости от покупки эти вещи появляются в игре или каким-либо образом влияют на игру. Еще один способ взаимодействия зрителей с игрой — опросы мода. Выбор в этих опросах во многом зависит от того, что включено в моде.

## Что такое монеты?

Монеты — это валюта мода. Посмотреть свой баланс можно с помощью "!баланс" команды. 

{% if utils == true %}
You'll notice the balance command may have some new emojis. If that's the case, here is an overview
of the emojis as follows:

- 💰 represents the amount of coins you current have.
- ⚖ represents your current karma.
- 📈 represents the amount of coins you gain everytime the mod awards coins.
- 📉 represents the amount of coins you lose everytime to mod awards coins.

{% endif %}


{%- if lootboxes == true -%}
You'll also notice that you'll get a message from the bot about a lootbox. You can open this lootbox
by using the `!openlootbox` command, as well as check the number of lootboxes you have with `!lootboxes`.
You'll always get a new lootbox everyday.
{%- endif -%}


<br/>
## Что такое Карма?

Карма — это система в моде, которая пытается ограничить количество негативных событий, которые зритель может приобрести за один раз. Эта система работает путем прямого изменения количества монет, которые зрители получают каждый раз, когда мод награждает монетами. Это означает, что чем ниже ваша карма, тем меньше ваш выигрыш в монетах. Есть надежда, что негативные события будут распространяться дальше, и колония сможет восстановиться.

## Как использовать Twitch Toolkit?

Вы можете использовать Twitch Toolkit несколькими способами, наиболее известный из которых — использование его
[commands]({{- "/commands" | relative_url -}}). Более важной командой является `{{- buy -}}` 
команда, которая является точкой входа модов в покупку вещей в магазине. Другими примечательными командами являются команды, которые позволяют вам видеть различную информацию о вашей пешке. Мы не будем рассматривать здесь каждую команду, но большинство команд, как правило, должны быть самоописательными или иметь описание того, что они делают, на странице [commands]({{- "/commands" | relative_url -}}) .


{%- if puppeteer -%}
<br/>
## What is Puppeteer?

[Puppeteer](https://steamcommunity.com/sharedfiles/filedetails/?id=2057192142) is a mod by Brrainz that
allows viewers to directly control their pawns, and even view a number of information about your pawn in
a graphical way. It also redirects some of the responses from Twitch Toolkit to its website to clean up
chat a bit. So, if you're logged into Puppeeter and you're wondering why the bot isn't responding to you,
you should check the `TT` tab on the website first.
{%- endif -%}
