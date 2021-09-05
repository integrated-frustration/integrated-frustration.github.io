---
layout: page
title: Power & Batteries
description: >
  Setting up the Batteries and Power Supply
hide_description: true
sitemap: false
categories: [drone]
---


<h3 class="faded">{{ page.description }}</h3>

1. TOC
{:toc}


### What is a Power Distribution Board?
A Power Distribution Board is a circuit used to power modules that cannot be connected to the LIPO directly because of a voltage difference. 
{:.def}

For example for powerful ESCs that accept voltages 6S+ a power module would be needed to power FCUs, FPV modules because they generally accept only $$5 V$$ to $$12 V$$.

### What does a BEC do?

A BEC or Battery Eliminator Circuit acts as a constant power supply with lower voltages. 
{:.def}

This is especially useful for powering components that require less than the ESCs voltage, thus avoiding the need for a Power Distribution Board. The only downside to using these is the cost and added weight for the ESCs.

### What is LIPO cell (S) configuration and how is it different from mAh?

In a LIPO each cell has a voltage range of $$4.2 V$$ to $$3.5 V$$. Each cell adds $$~3.7 V$$ to the total (in series connections, the voltage is summed).
{:.def}

The ideal voltage to store and start charging a LIPO is around $$3.7 V$$ (this varies by manufacturer).

For example if we have a 4S battery, it means that there are 4 cells in series. The subsequent voltage will be: $$4 \times 3.7 V = 14.8 V$$  

The mAh rating, on the other hand, is simply the amount of charge a battery can hold or how long the battery will last based on the current drawn. So, a $$4000 mAh$$ battery will provide upto $$4 A$$ continuously for an hour, or $$400 mA$$ over 10 hours, $$40 mA$$ over 100 hours, etc...
 
### Burst rate? C rate?

The burst rate is the amount of rated current that can be supplied by the battery for a very little amount of time.
{:.def}

This value is usually much larger than the regular continuous C rate of the battery. Usually, this level of draw should not be anything more than 10 seconds.

The C rate of a LIPO is the capacity of energy the battery can safely discharge. 
{:.def}

It's easy to calculate the amount of safe continuous current draw using the C rate. An example here should help clarify how to use this value. Let’s take our battery, it’s a 6S battery with a capacity of $$4000 mAh= 4 Ah$$. If the C rate is 60 then the fully charged battery is rated for $$4 \times 60 = 240 A$$ for an hour.

### Are LIPO batteries supposed to make up above 50% of my drone’s weight!

Possibly. This is especially true if you want to fly long range. Unfortunately, battery technology is still not as advanced as we would like it. LIPO batteries are very energy dense and 4 times denser than Nickel Cadmium batteries. This is why LIPOs are the king of high energy devices like drones, e-bikes, cars, etc. The reason that cars aren't using this battery type just yet is because they are very expensive, especially at the mAh rating cars require. 

### So many connectors! Which one do I choose for my drone?

A simple table that covers the [most common ones][connectors]{:target="_blank"}:

| Connector Type | Continuous Current Rate Supported (Amps) | Burst Rate Supported (Amps) |
|:--------------:|:----------------------------------------:|:---------------------------:|
| TX30 | 30 | ~60 |
| TX60 | 60 | ~90 |
| TX90 | 90 | ~120 |
| EC5 | 120 | ~150 |

If your drone connector is not here, simply Googling `<your connector type> current rating` will give you the answer. 
Try and buy your preferred connector with anti-spark. You can see our [troubleshooting][spark]{:target="_blank"} guide to see why this is a useful feature.
{:.rec}
 
### How do I use the LIPO battery charger?

We think a video would do great justice to this concept. We suggest the [following video][Battery]{:target="_blank"}.
 
### Can I connect components directly to my battery? Do I need a Power Distribution module?

ESCs and Power Distribution Boards can be directly connected to the battery. It is common for all other components(FCU, Receiver, etc.) to be connected using the ESCs BEC or the PD board.

### What is the difference between silicon wires and standard wires?

It's important to clarify that this is a common mistake. There is nothing like silicon wire, it's just that the wire has silicon insulation around it. The advantages of this silicon coating are that the wire is more heat resistant, flexible and has a higher amperage rating. If you would like to learn more [here][Silicon]{:target="_blank"} is an interesting video!

### How do I choose what wire gauge to get for my drone?

Depends on the current draw for your components. You can infer the gauge from the things the wire connects. For example, if you’re thinking about the gauge for wire between the battery and the rest of the circuit, then you need to calculate the total current drawn from all connected components. This includes the maximum current from all ESCs, flight controller and FPV equipment. If your RC receiver, GPS, etc. need external power then please add those values as well. Please refer to the image below to see what gauge is recommended for your current requirements.

![drone_gauge.jpeg](/assets/blog/drone_gauge.jpeg){: width="700px" loading="lazy" style="border-radius:25px"}

Continue with [ESCs](esc.html){:.heading.flip-title}
{:.read-more}

[Battery]: https://www.youtube.com/watch?v=RPzJOKoHhhQ&t
[Silicon]: https://www.youtube.com/watch?v=RHbj0TSTiEA
[connectors]: https://blog.ampow.com/rc-battery-connector-types/
[spark]: /drone/troubleshooting.html#when-connecting-my-lipo-to-the-drone-and-charger-i-see-a-spark