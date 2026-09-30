# week 1: rp2040 dev board & mini hackpad

## project goals
* **Target Specs:** custom RP2040 microcontroller board using the QFN-56 package, 16MB QSPI flash, 12MHz crystal oscillator, USB-C connector with 5.1k CC pull-down resistors, and dual-row breakout headers for all GPIO pins to drive a mini hackpad.
* **Design Philosophy:** build a functional dev board from absolute ground zero using the hack club stasis guide so i finally understand what goes on under the hood of a raspberry pi pico [instead of treating microcontrollers like magic black boxes].
* **Why I'm building this:** week 1 theme is PCB, and i needed a custom board to integrate with an old mini hackpad design i had lying around. also i wanted to suffer through routing 0402 passives and tiny IC pins.

## bill of materials (BOM)
* refer to `bom.csv` in this folder for the full list of parts including the RP2040 MCU, W25Q128 flash chip, LDO voltage regulator, buttons, and passive components.

## dev journal - part 6: left-side GPIO routing (the lost footage)
* **Time spent:** 2 hours
* **Recorded on lapse:** no [because my brain shut off and i forgot to hit record]

this was easily the most painful part of the entire week. of course, this is the exact 2-hour block where i forgot to start the lapse recording, so you'll just have to take my word for it that i was working and not staring blankly at a wall.

since this was my first time designing an RP2040 board from scratch, trying to connect the RP2040 pins to the left-side GPIO headers turned into a complete trace-routing nightmare. i was following the hack club stasis guide (`stasis.hackclub.com/starter-projects/devboard`), but making clean connections for GPIO0 through GPIO15 without crossing traces or creating illegal angles felt like playing a high-stakes game of snake. 

i had to pause every 5 minutes to watch multiple youtube tutorials on KiCad trace routing, net classes, and how to use vias without making the PCB look like cheese. i kept triggering Design Rule Check (DRC) errors because my traces were either too close to the ground plane or running over decoupling capacitors. after two hours of tearing my hair out, re-routing lines three times over, and wrestling with via placements, the left side is finally connected and fully routed. 

## visual showcase

![complete pcb layout preview](images/preview.png)
*(the fully routed RP2040 dev board before sending it off to the fab house)*