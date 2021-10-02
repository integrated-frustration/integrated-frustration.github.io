---
layout: page
title: Circuit Construction & Decoding
description: >
  Overview of the Arduino development process
hide_description: true
categories: [arduino]
---


<h3 class="faded">{{ page.description }}</h3>

1. TOC
{:toc}

### Circuit Construction

1. The circuit was made using EasyEDA’s platform; it's completely free and can be downloaded from [here][easyeda]{:target="_blank"}.

2. The circuit file can be downloaded from [here][circuit]{:target="_blank"}.

3. After you perform your analysis on the circuit you can then move to the PCB design stage.

4. In EasyEDA click `Design > Convert Schematic to PCB > No, Keep Going`. A shortcut is just pressing `Alt + P`.

5. It will ask you then for board measurements. You can use the standard Arduino Uno specifications found [here][unospec]{:target="_blank"}.

    Tip: If you want to save time and not make the right indentations just make the board using the max dimensions of $$L \times B = (2.7 \times 2.1) inch$$

6. You can now restructure, modify the PCB any way you wish! Save the file and use any PCB manufacturer of your choosing.

### Circuit Decoding

1. If you want to just see what connects where open the schematic file from [here][schematic]{:target="_blank"} or see the image below.

<a href="/assets/blog/arduino_schematic.png" target="_blank">
<img src="/assets/blog/arduino_schematic.png" alt="/assets/blog/arduino_schematic.png" loading="lazy" style="border-radius:25px" width="350px" >
</a>


2. Open the generated Gerber file from [here][gerber]{:target="_blank"} and then trace the path of the components.

Credit: [Instructables](https://www.instructables.com/DIY-Arduino-UNO-How-to-Make-Your-Own-Arduino-Uno-B/
){:.faded}

[unospec]: https://www.oreilly.com/library/view/arduino-a-technical/9781491934319/ch04.html
[schematic]: https://drive.google.com/file/d/1U32lmq1rE9bE1_Zn98m9rc7GlrSqoneg/view?usp=sharing
[gerber]: https://drive.google.com/file/d/1oBXNmvye1zQEywYx9mK3N-7npWY6DJ9b/view?usp=sharing
[easyeda]: https://easyeda.com/page/download
[circuit]: https://drive.google.com/file/d/1U32lmq1rE9bE1_Zn98m9rc7GlrSqoneg/view?usp=sharing