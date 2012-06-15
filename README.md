fxchat
======

A collection of tools for forex discussions over IRC.

1. [Introduction](#introduction)
2. [Installation](#installation)
    1. [Requirements](#requirements)
    2. [Ømq](#zeromq)
    3. [Metatrader](#metatrader)
    4. [Phenny](#phenny)
3. [Commands overview](#commands)
4. [Advanced Configuration](#configuration)

<a name="introduction"/>
1. Introduction
---------------

Never trade alone.

You can see a bot running here [irc://chat.ircforex.com/eurusd](irc://chat.ircforex.com/eurusd).

> [10:59:15] `<daydayprofit>` .eu bulls h1 14
>
> [10:59:16] `<cortex>` -0.00190668;EURUSD;iBullsPower;60;14
>
> [16:15:12] `<naiv>` .uj
>
> [16:15:12] `<cortex>` 79.494 | 79.504 | Low 79.355 | High 79.673 | UTC 14:15:10
>
> [16:43:41] `<naiv>` .time Chicago
>
> [16:43:42] `<cortex>` it's 09:43 CDT-0500 in Chicago (14:43 UTC)
>
> [16:43:53] `<naiv>` .place New York
>
> [16:43:53] `<cortex>` New York will close in 5h17

<a name="installation"/>
2. Installation
---------------

The following procedure was realized with GNU/Linux Debian unstable.

<a name="requirements"/>
### 2.1 Requirements

* [Wine development release](#www.winehq.org) - Run Windows applications on Linux
  With debian it's easier to use [wine-unstable](#http://dev.carbon-project.org/debian/wine-unstable/)
* [Metatrader 4](#www.metatrader4.com) - Forex Trading Platform
  If your broker distributes a specific version, you might want to use it.
  I don't know if the tools will work under Metatrader 5, please leave me a message if you tried it.
* [Phenny](#inamidst.com/phenny/) - Python IRC bot

<a name="zeromq"/>
### 2.2 Ømq

[Ømq](#http://www.zeromq.org) is a socket library that we will use to exchange messages between MT4 and fxchat.

    sudo apt-get install libzmq-dev

The python library.

    sudo easy_install pyzmq

<a name="metatrader"/>
### 2.3 Metatrader

#### [ZeroMQ asynchronous communication](http://codebase.mql4.com/7147)

This is a Ømq library for MT4.

Auto installation.
     Get commando.zip here http://codebase.mql4.com/7147
     Run commando.exe

You can also compile it but at the moment I'm writing the code isn't up to date.
    Get zmq.zip here http://codebase.mql4.com/7147
    Follow the instructions

#### fxchat.

Install the fxchat script for MT4.

    # Configure the path to your metatrader directory
    MT4="~/.wine/drive_c/Program Files/OANDA - MetaTrader/"

    cp Fxchat.mq4 $MT4/experts/scripts/

In the metaeditor, open the fxchat script, compile it, then drag it over a chart to activate it.

<a name="phenny"/>
### 2.4 Phenny

Install the fxchat script for phenny.

    # Configure the path to your phenny directory
    BOT="~/cortex/phenny/"

    cp fxchat.py $BOT/modules/

<a name="commands"/>
3. Commands overview
--------------------

Say *.help* in a channel where the bot is hanging.

<a name="configuration"/>
4. Advanced configuration
-------------------------

In construction.
