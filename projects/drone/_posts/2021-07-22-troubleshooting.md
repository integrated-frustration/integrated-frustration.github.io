---
layout: page
title: Troubleshooting
description: >
  Solving Common Frustrations
hide_description: true
sitemap: false
categories: [drone]
---


<h3 class="faded">{{ page.description }}</h3>


1. TOC
{:toc}


### My LIPO charger is getting quite hot when charging!

When charging your LIPO on the **balanced mode** (as you always should) you may notice it gets hot to the touch. Uncomfortably hot. 
This heat can vary based on how far you are pushing your charger. If you use the upper limits of your charger like our 6S LIPO with a 4C charging rate, you will most likely experience this. 

Place a small **fan** near the adapter and charger. It will dramatically reduce the operating temperature.
{:.rec}

### My wires are quite hot after running the drone on max power for a little bit

Most likely your drone’s wiring is very close to the rated threshold current of the wire gauge you are using. Using a lower gauge wire can fix this problem. It will improve the overall performance of your drone and be safer too.

### My drone motors are quite hot! 

Drone motors can be almost 70&deg;C when running at full power for even half a minute. It is most likely normal as long as there is no smoke, fire or sparks visible from the motor. Please see our drone motor sheet below to estimate expected operating temperatures.

![Motor Sheet](/assets/blog/drone_motor_specs.jpeg){: width="700px" loading="lazy" style="border-radius:25px"}

### My motor is spinning in the wrong direction!

Two possible fixes:
* The easiest and safest is to reverse it from the Ground Control software you are using (Mission Planner/BetaFlight/etc). To do this in Mission Planner go to the `Setup -> Mandatory Hardwarer -> Servo Output` and simply click reverse on the appropriate motor number. 
* If that doesn't work, try [changing][spin]{:target="_blank"} any two wires that connect your ESC and the motor in question.

### My drone is unstable and can't take-off!

Ensure that your motors are __spinning in the right directions__ and are __correctly numbered__ in the FCU. To test this, use the `Additional Hardware -> Motor Test` option in Mission Planner and confirm that your setup conforms to one of [these][motortest]{:target="_blank"}. 

If this is not the cause, it's likely due to:
* Accelerometer Calibration - ensure you hold your drone *still* in each calibration position
* Electromagnetic Interference - calibrate your sensors away from electronics and power lines
* Insufficient Power - ensure your battery is charged and that the FCU and ESCs are powered
* Flight Mode - take-off in the Stabilize mode. Other modes may cause unexpected behavior

![Drone Crash](/assets/blog/drone_crash.gif){: width="500px" loading="lazy" style="border-radius:25px"}

### My ESCs beep continuously! What’s wrong?

The following troubleshooting section helped us hugely! If the problem persists, try to reinstall the OS on your drone as well as your Ground Control Station (e.g. Mission Planner). Triple check your wiring and ensure there are no shorts. If that doesn't work, you may have a defective ESC.

![ESC Beep](/assets/blog/drone_esc_beep.jpg){: width="700px" loading="lazy" style="border-radius:25px"}

Credit: [DamoRC][ESCError]{:target="_blank"}{:.faded}

### Why is my compass calibration taking so long?

Compass calibration can take up to 10 minutes at times especially if you are running it on slower devices like the Raspberry Pi 2. Also, electromagnetic interference from electronic devices and power lines can delay the process and make it less accurate. Just ensure you follow the calibration motions and confirm that your Telemetry (WiFi/UART) is always connected to the Ground Control Station. If this may be a problem, you can calibrate using just your [RC Transmitter][compass]{:target="_blank"} too!

### Why are the nuts and screws in my drone so tight?

Drone frames and components use nylon threaded nuts, meaning that you would need a screwdriver and pair of pliers to hold the nut while screwing it. This is done so that the joints are strong but also to prevent excess vibration mid flight.

### My FCU's connectors are tight to plug in and almost impossible to remove!

We encountered something very similar with our Navio2. We found that [buying DF13 connectors][DF13]{:target="_blank"} externally was an effective solution. You would need two 6 pin connectors and one 4 pin connector for UART, ADC ports and I2C port respectively.

### My GPS signal is poor!

This is most likely because of eletromagnetic interference. Alternatively, your GPS may not have a direct line of sight with the sky. The interference from the Camera/Radio Receiver/FCU/etc can quickly and severely deteriorate GPS accuracy. 

Use a GPS mount to move the module as far away from other electronics as possible. Avoid flying indoors if you want to use GPS navigation since your signal will likely be very weak.
{:.rec}

### When connecting my LIPO to the drone, I see a spark! 

This is surprisingly normal if your battery has a high `S/mAh` count. The spark is because of the fast charging of the ESCs capacitors, even if you have a filter capacitor on the Power Distribution board (PD). When connecting your drone it is important to be cautious of any excessive heating of the **LIPO, ESCs or PD**. Any burn marks usually indicate a problem with the component or wrongly calculated power requirements. To prevent your drone from getting damaged:

* __Triple-check__ all calculations before ordering any components. A simple trick is to add all the components to your cart and then check power requirements from scratch
* When starting the drone for the first time, attach all your components first, excluding only the propellers. Generally, a __larger load will reduce the spark intensity.__
* Try to __angle the connector so the positive terminal connects first__. Wait for about 3 seconds and then connect the negative terminal. This works because when the positive side is connected it goes through the whole circuit and then when the negative side touches the discharge is far lesser hence reducing the spark
* Buy the __anti spark-version__ of your connector, if available. It will be safer and quicker to connect up

It’s perfectly normal if you cannot connect it on your first-time. The spark is quite a surprise! Just remember, if you see a big spark many times (20+ in our experience), your connector will start to blacken and wear off.

![Drone Spark](/assets/blog/drone_spark.gif){: width="500px" loading="lazy" style="border-radius:25px"}

Credit: [YouTube](https://youtu.be/xF8GqpqKYlA){:.faded}

Continue with [General](../general){:.heading.flip-title}
{:.read-more}

[ESCError]: https://forum.flitetest.com/index.php?threads/esc-constant-beep-no-solution.39196/
[DF13]: https://www.aliexpress.com/item/32718835617.html?spm=a2g0o.search0304.0.0.5d91529e94SY3E&algo_pvid=9ae26a45-bb46-4851-b06a-39f6129bf055&algo_exp_id=9ae26a45-bb46-4851-b06a-39f6129bf055-0
[motortest]: https://ardupilot.org/copter/docs/connect-escs-and-motors.html
[spin]: https://oscarliang.com/change-motor-spin-direction-quadcopter/
[compass]: https://ardupilot.org/copter/docs/common-compass-calibration-in-mission-planner.html#onboard-calibration-using-stick-gestures-no-gcs
