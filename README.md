STM32F4-Discovery-example-code
==============================

This is a fork of ChibiOS/RT example project originally written by Mathias-L, available on GitHub (https://github.com/Mathias-L/STM32F4-Discovery-example-code).

I made it work on ChibiOS/RT 2.7.0unstable, on git revision f48d4bac4355916f56b531eb117f9732bbf9bb7b (8 Sep 2013). I also applied change from here: http://forum.chibios.org/phpbb/viewtopic.php?f=4&t=514&start=10#p5363

Compiled with GCC ARM Embedded (https://launchpad.net/gcc-arm-embedded) version 4.7-2012-q4 (GCC 4.7.3).

Original README
===============

This is my example code for the STM32F4 Discovers using the RTOS ChibiOS.

requirements
------------
* Chibios 2.5.0+ (or a recent development snapshot)
* arm toolchain (e.g. arm-none-eabi from summon-arm)

features
--------
* serial over USB console
* PWM initialization and control
* ADC measuring, continuous and single scan
* background blinker thread
* code structured into separate files

usage
-----
* edit the Makefile and point "CHIBIOS = ../../chibios" to your ChibiOS folder
* make
* connect the STM32F4 Discovery with both USB connectors
* flash the STM32F4: st-flash write build/ch.bin 0x8000000
* use your favorite terminal programm to connect to the Serial Port (/dev/ttyACM0 for me, probably COM1 on Windows)

console commands
----------------
* help
* exit
* info
* systime
* mem
* threads
* toggle 1/2/3/4 (toggles #led, short: t)
* blinkspeed #speed (changes blinker period to #speed ms, short: bs)
* cycle #duty (changes the duty cycle of PWM1 to #duty, short: c)
* ramp #from #to #step \[delay\] (creates a ramp for PWM1 with the given parameters, short: r)
* measure (measures 16384 analog samples on pin PC1 and prints the first and the average, short: m)
* measureAnalog (measures 16384 samples and converts the average to Volts, short: ma)
* measureDirect (measures 16384 samples and prints them all, short: md)
* measureContinuous (starts a background analog conversion, short: mc)
* readContinuousData (prints what has been collected by the background conversion, short: rd)
* stopContinuous (stops the analog conversion, short sc)





disclaimer
----------
Neither am I a good C programmer nor do I have extensive knowledge about 
ChibiOS, the STM32F4 or uCs in general. I wrote this code to make myself
familiar with the STM32F4 Discovery and I figured ChibiOS was a usefull tool.
From my POV the code is not that bad, but your opinion may differ. In
that case, please don't laugh at my code but provide constructive criticism.
I just realized: I'm no pro at Git, Github and Markdown either...

Since I started from the USB-CDC code example from ChibiOS which is GPLv3,
I think I am forced to release this code under GPLv3 though I don't care what you do
with the code. I asked Giovanni and he said "there is not much meat" in it anyways.

