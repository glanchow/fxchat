fxchat
======

A collection of tools for forex discussions over IRC

1. [Introduction](#introduction)
2. [Installation](#installation)
2.1 [Requirements](#requirements)
2.2 [Metatrader](#metatrader)
2.3 [Phenny](#phenny)

<a name="introduction"/>
1. Introduction
---------------

Never trade alone.

You can see a bot running here [irc://chat.ircforex.com/eurusd](irc://chat.ircforex.com/eurusd).

> [10:59:15] <daydayprofit> .eu bulls h1 14
>
> [10:59:16] <cortex> -0.00190668;EURUSD;iBullsPower;60;14
>
> [16:15:12] <naiv> .uj
>
> [16:15:12] <cortex> 79.494 | 79.504 | Low 79.355 | High 79.673 | UTC 14:15:10
>
> [16:43:41] <naiv> .time Chicago
>
> [16:43:42] <cortex> it's 09:43 CDT-0500 in Chicago (14:43 UTC)
>
> [16:43:53] <naiv> .place New York
>
> [16:43:53] <cortex> New York will close in 5h17

<a name="installation"/>
2. Installation
---------------

<a name="requirements"/>
### 2.1 Requirements

* Phenny - Python IRC bot
* Metatrader - Forex Trading Platform

<a name="metatrader"/>
### 2.2 Metatrader

    # Configure the path to your metatrader directory
    MT4="~/.wine/drive_c/Program Files/OANDA - MetaTrader/"

    cp Fxchat.mq4 $MT4/experts/scripts/
    pushd /dev/shm
    touch fxchat-mt4 mt4-fxchat
    cd $MT4/files
    ln -s /dev/shm/fxchat-mt4 fxchat-mt4
    ln -s /dev/shm/mt4-fxchat mt4-fxchat
    popd

Open metatrader and its metaeditor, find the fxchat script, compile it.
Then drag it over a chart to activate it.

<a name="phenny"/>
### 2.3 Phenny

    # Configure the path to your phenny directory
    BOT="~/cortex/phenny/"

    cp fxchat.py $BOT/modules/
