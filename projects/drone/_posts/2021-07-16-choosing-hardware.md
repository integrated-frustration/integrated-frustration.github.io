---
layout: page
title: Choosing Hardware
description: >
  Costs, Frames, Flight controllers and More!
hide_description: true
sitemap: false
categories: [drone]
---


<h3 class="faded">{{ page.description }}</h3>

1. TOC
{:toc}

Before starting this section, we suggest reading the [Troubleshooting][trouble]{:target="_blank"} and [General][general]{:target="_blank"} section.

Have a discussion about the _costs_ of building your drone. It’s not cheap! We suggest setting up a budget before you start planning. But more importantly, ask yourself what goals you have for your project? If you’re on a budget, try to optimize only 2-3 aspects of your drone (i.e. autonomy, flight duration, range, FPV, speed, etc). __Otherwise, your project’s costs and complexity may quickly get out of hand!__


### Choose your flight controller

This varies based on your chosen optimization. In our case, we wanted a hybrid that can perform all the requirements mentioned above, to maximize our learning experience. So, we used the Navio2 with a Raspberry Pi 4. Another common build is for racing where the primary focus is to select a lightweight FCU. Once you have selected a FCU, note down its weight and proceed to the next step.

### Select motors, LIPOs, ESCs and propellers

These steps are interdependent, so they should be considered simultaneously. 

1. Every frame has size restrictions that determine which motors and propellers can be mounted (defined usually by a number like 2205). After you have the compatibile motors, you should look at the amount of lift your motors generate at various throttle levels from the motor specification sheet. It should look something like:

    ![drone_motor_specs.jpeg](/assets/blog/drone_motor_specs.jpeg){: width="700px" loading="lazy" style="border-radius:25px"}

2. Then, look at the current being drawn when the motor is at maximum throttle with your specific propellor choice. This will give you the amperage for your ESCs. 

    If you are not using a Power Distribution module, please ensure your chosen ESCs have a Battery Eleminator Circuit capable of meeting your FCU's power requirements.
    {:.warn}

3. Next, you should check what battery cell configuration can be used with the motors and ESCs you have chosen. Usually motors accept a range of battery cell configurations (e.g 4S-6S). Once you select the cell configuration that works with your ESCs and motors it's time to select an appropriate `mAh` value. Use [this calculator][bat]{:target="_blank"} and see the estimated time your drone will fly by changing the `mAh` value. It's also worth noting how the time changes as you vary the flying load (throttle).

4. Once you select the battery add the following weights in grams: 
  ~~~
  Frame + Motors + Battery + Flight Controller + ESCs + Power Distribution Module + 70
  ~~~ 

    We have decided to add 70 grams as a good measure for the receiver, GPS and wiring.
    {:.figcaption}

    This weight estimate does not include any FPV equipment! If you wish to add FPV please select a transmission module and camera and add those weights too. They are usually an additional 30 grams.
    {:.warn}

5. Once you get your total weight use [this calculator][motor]{:target="_blank"} to see if your drone can lift off! A ratio of `2:1` is good to fly and program with. But! Having a higher ratio means you need less power to fly, which means you can use your motors at more efficient speeds.

If your drone has a lower ratio, just go back and find a compatible motor that gives you your required level of thrust.

An easy way to skip this step/ confirm your choices is to pay 1$ and use [the following website][pay]{:target="_blank"} to see if your drone hardware is compatible. It's a small price to pay for a lot of peace of mind. 
{:.rec}

### Selecting a transmitter and receiver 

This may seem simple but when you start the process it can get really confusing (see our section on [RC][rc]{:target="_blank"}). 

Ensure that your Receiver and Transmitter share at least __ONE__ protocol to communicate with each other!

[trouble]: ../drone/troubleshooting.html
[general]: ../drone/general.html
[rc]: ../drone/radio-communication.html

[motor]: https://www.omnicalculator.com/other/drone-motor
[bat]: http://multicopter.forestblue.nl/lipo_need_calculator.html
[pay]: https://www.ecalc.ch/xcoptercalc.php