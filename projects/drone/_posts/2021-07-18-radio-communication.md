---
layout: page
title: Radio Communication
description: >
  RX/TX, Communication Protocols and Telemetry
hide_description: true
sitemap: false
categories: [drone]
---


<h3 class="faded">{{ page.description }}</h3>

1. TOC
{:toc}

### What on earth is RX/TX in RC systems?

RX = Receive and TX = Transmit. In drones, this usually refers to an RC Receiver and Transmitter/Controller
In any connection system, there has to be at least one thing to transmit (TX) messages and another to receive (RX) them. 
{:.def}

But mostly, components do both and so, you see these two terms on the same device. For example, FCUs have ports for both TX and RX since they need to transmit data from the sensors/ESCs to the pilot *AND* they need to receive commands from the pilot too.

![drone_radio.jpg](/assets/blog/drone_radio.jpg){: width="700px" loading="lazy" style="border-radius:25px"}

From left to right: the FCU, Receiver and Transmitter in our drone.
{:.figcaption}

### Understanding the many communication protocols

In communication systems, there are physical ports like the [UART][UART]{:target="_blank"} which connect two systems together by some wire (like the FCU and the Radio Receiver). There can also be wireless connections via antennas and radio waves (like between the Radio Receiver and Transmitter). 

But in both cases, there needs to be some language that organizes the messages sent between these systems. These are the communication protocols. They allow signals between the ports to have variety so that they can communicate everything from the speed of the motors to the GPS location to the battery voltage and more. So when searching for devices that talk to each other, ENSURE that they share **at least one** protocol like [SBUS/PWM/PPM/etc][SBUS/PWM/PPM]{:target="_blank"}. 

Some common points to check for protocol compatibility in a drone:

  * Radio Transmitter - Radio Receiver
  * FCU - Radio Receiver
  * FCU - ESC
  * FCU - Telemetry

[MAVLINK][Mavlink]{:target="_blank"} is one such protocol used for communicating telemetry data from the FCU to the pilot’s Transmitter or a Ground Control Station.

### Why are some RC Transmitters/Controllers so expensive? What should I get?

Some RC Controllers have an excellent internal antenna which is usually the greatest cost increase. Other factors like a touch screen, hall gimbals, protocol support and even ergonomic design proportionally increase the cost of the Controller. A good product line where we can clearly see such cost increments is from the Radiomaster TX12, TX16, TX16S Max. Use [this link][RadioMaster]{:target="_blank"} and have a look at `Products -> Remote Controls`.

### Is RC the same as Telemetry?

No… These are two related but different systems. Both of them generally use radio waves to communicate, have connections to the FCU and can sometimes be packaged into a single device.  

BUT! RC (Radio Control) is generally a connection between your Radio Transmitter and Receiver that gives commands to your FCU to fly the drone. However, Telemetry is the flight data (location, altitude, battery level, video, etc.) your FCU sends back to you for monitoring and guidance. So, you can fly without Telemetry but not without some kind of RC (unless its autonomous). Some options for Telemetry include using WiFi, Bluetooth or another dedicated Radio Transmitter onboard to send out flight data. Recently, Radio Receivers have dual functionality and can both receive commands and send back Telemetry data.
 

[UART]: https://www.circuitbasics.com/basics-uart-communication/
[SBUS/PWM/PPM]: https://www.youtube.com/watch?v=y7T4hBqOwxM
[Mavlink]: https://mavlink.io/en/about/faq.html
[RadioMaster]: https://radiomasterrc.com/