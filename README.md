# Avalon Project
> Avalon "The isle of the dead, an island paradise where King Arthur and other heroes are taken after death"

The Avalon Project is an open-source Self-Balancing-Electric-Skateboard project focused on affordability, power, and usability. All PCB, CAD, Code and project files can be find inside this repository.
## Lineup:
- [Odyssey](#odyssey) Flagship 134.4V 1KWh+ Performance System
- [Pathfinder:](#pathfinder) Capable 138.8V 500Wh+ Pocket Rocket (ETA Q4 2024)
- [Questor:](#questor) Powerful 100.8V 400Wh+ Lightweight Commuter (ETA Q1 2025)

>See also: [InfoBar](#infobar), E-ink external display for the Avalon Series

# Odsyssey
> The _Odyssey_ is a timeless epic by Homer, chronicling Odysseus's perilous 10-year journey home after the Trojan War.

The Odyssey is the Flagship board in the Avalon Series of self-balancing boards. Boasting a voltage range of 100.8V to 134.4V, 1KWh+ of capacity, 700+ Lumen lighting, IMU wake detection, no compromises were taken during the design process. 
### Features
- Voltage(V): 134.4V to 100.8V
- Range(Km): 56-95 (134.4V), 40-65 (100.8V)
- Speed: [Yes](https://www.youtube.com/watch?v=zXf44tSWhBQ) (Over 2000W+ compared to video)
- 10 x [70-100 Lumen White LEDs](https://www.lcsc.com/datasheet/lcsc_datasheet_2309141627_JNJ-OPTOELECTRONICS-JNJ-LTJH0111W60-26mil-8000-9000K_C7500127.pdf) (PWM Configurable)
- 22 x [SK68812RGBW](https://cdn-shop.adafruit.com/product-files/2757/p2757_SK6812RGBW_REV01.pdf) Addressable LEDs
- [Fingerprint Sensor](https://cdn.shopify.com/s/files/1/0176/3274/files/104474-datasheet.pdf?v=1650622001) with user profiles and logging
- [ESPHome](https://esphome.io/) integration
 > Control Boards are designed for expandability. A powerful and efficient 5V rail is integrated into the Schematics, but not the PCB or BOM. See [files](Odyssey/Control%20Board/PCBs/EasyEDA) for more information.

### Powertrain 
- Controller: [JetFleet F6](https://www.jetfleet.store/product/15108255/controller-jetfleet-f6), [TRONIC X12](https://tronicsystems.com/products/x12-bareboard-no-enclosure), [ENNOID-ESC MK8](https://www.ennoid.me/esc/150v-esc)
- BMS: [ENNOID-BMS Master-XLITE](https://www.ennoid.me/bms/master-xlite), [ENNOID-BMS XLITE-V4](https://www.ennoid.me/bms/xlite-v4), [Flipsky 4S-30S 20A BMS](https://flipsky.net/collections/bms/products/flipsky-4s-30s-20a-bms-protection-board-hardware-ternary-polymer-lithium-battery-only-charge-bms-board-for-onewheel-ebike-eskateboard-euc)
- Cells: [Molicel P42A](https://www.molicel.com/wp-content/uploads/INR21700P42A-V4-80092.pdf), [Molicel P45B](https://www.molicel.com/wp-content/uploads/INR21700P45B_1.2_Product-Data-Sheet-of-INR-21700-P45B-80109.pdf), [Samsung 50S](https://www.dnkpower.com/wp-content/uploads/2022/07/SAMSUNG-INR21700-50S-Cell-Specification.pdf), [EVE 40P](https://www.rcscomponents.kiev.ua/datasheets/INR21700_40P.pdf?srsltid=AfmBOor8f9CQmFkExNRTm6Mq1A_Q03pWzBJgzzz9d33UfN2aQRMcYi1Q), [Samsung 40T](https://www.dnkpower.com/wp-content/uploads/2019/02/SAMSUNG-INR21700-40T-Datasheet.pdf), [TenPower 40TG](https://www.tenpowercell.com/wp-content/uploads/2022/12/TP-INR21700-40TG-Product-Datasheet-v1.4.1.pdf), [Sony VT6A](https://www.imrbatteries.com/content/murata_us21700vtc6a.pdf)
> If you are unsure what Cell, Controller or BMS to use for this board, consider consulting an experienced VESC builder for assembly assistance. Please refer them to this repository

## Primary Parts

- [Odyssey Control Board](#odyssey-control-board)
- [Odyssey Lightsym Bars](#odyssey-lightsym-bar)
- [Odyssey Controller Box](#odyssey-controller-box)
- [Odyssey Battery Box](#odyssey-battery-box)
- [Odyssey Rails](#odyssey-rails)
- [Odyssey Footpads](#odyssey-footpads)
- [Odyssey Bumpers](#odyssey-bumpers)
- [Odyssey Fender](#odyssey-fender)
- [Odyssey Axle Blocks](#odyssey-axle-blocks)

## Odyssey Control Board
The **Odyssey Control Board** is designed inside [EasyEDA](EasyEDA.com) and is intended to be assembled using [JLCPCB Economic Assembly](https://jlcpcb.com/capabilities/pcb-assembly-capabilities). 

[EasyEDA Files](Odyssey/Control%20Board/PCBs/EasyEDA)
[ESP32 Code + Flashing](Odyssey/Control%20Board/Code)

The Control Board communicates with/powers:

- The R503 Fingerprint Sensor
- 2 x [Odyssey Lightsym Bars](#odyssey-lightsym-bar)
- ESP Home integration using an [Espressif Systems ESP32-WROOM-32E-N8](https://www.lcsc.com/datasheet/lcsc_datasheet_2403071012_Espressif-Systems-ESP32-WROOM-32E-N8_C701342.pdf) as the [MCU](https://en.wikipedia.org/wiki/Microcontroller)
- VESC Power ([SSR Relay](https://www.lcsc.com/datasheet/lcsc_datasheet_1808101047_TOSHIBA-TLP172GM-TPL-E-O_C261926.pdf) control)

You will also need to purchase parts from [Digikey](https://www.digikey.co.uk/en/mylists/list/NP048JOWBK). These parts are not available in the JLCPCB parts library and will need to be assembled separately. 
> The Odyssey Control Board is uses a high voltage DC input. Ensure proper safety measures are used to prevent damage to ~~battery~~ everything ~~within 5 mile radius~~.



## Odyssey LightSym Bar

The **Odyssey LightSym Bar** is designed inside [EasyEDA](EasyEDA.com) and is intended to be assembled using [JLCPCB Economic Assembly](https://jlcpcb.com/capabilities/pcb-assembly-capabilities). 

[EasyEDA Files](Odyssey/LightSym%20Bar/PCBs/EasyEDA)

The LightSym Bar has 15 inputs:
- 5 x 5V
- 2 x 3V3
- 2 x NTC100K
- 2 x BRTL
- 2 x BRTR
- 1 x Din
- 1 x GND

The labels on these inputs correlates with the labels on the [Odyssey Control Board](#odyssey-control-board).

You will also need to purchase parts from [Digikey](https://www.digikey.co.uk/en/mylists/list/NP048JOWBK). These parts are not available in the JLCPCB parts library and will need to be assembled separately. 


## Odyssey Controller Box
The **Odyssey Controller Box** has capacity for 24S2P 21700. For cell options, please see the [Powertrain](#powertrain) section. 

[CAD Files](Odyssey/Controller%20Casing)
### Features:
- **Dual** [TPU](https://formlabs.com/uk/blog/complete-guide-tpu-3d-printing/) O-ring
- [GX16](https://www.sunrom.com/download/663.pdf) Charge port
- M20 Gland Hole
- Steel reinforcement bolt system

### Hardware
- M3x8mm CSK Pozi
>See the [3D Printing Guidelines](#3d-printing-guidelines) for information on how to manufacture this box.

## Odyssey Battery Box
[CAD Files](Odyssey/Battery%20Casing)

>See the [3D Printing Guidelines](#3d-printing-guidelines) for information on how to manufacture this box.

## Odyssey Rails
[CAD Files](Odyssey/Rails)



## Odyssey Footpads
[CAD Files](Odyssey/Footpads)

>See the [3D Printing Guidelines](#3d-printing-guidelines) for information on how to manufacture this box.

## Odyssey Bumpers
[CAD Files](Odyssey/Bumpers)

## Odyssey Fender
[CAD Files](Odyssey/Fender)

>See the [3D Printing Guidelines](#3d-printing-guidelines) for information on how to manufacture this box.

## Odyssey Axle Blocks
[CAD Files](Odyssey/Axle%20Blocks)

# InfoBar
The InfoBar is an [ESPHome](https://esphome.io/) based [E-ink display](https://www.waveshare.com/4.2inch-e-paper-module.htm) with [Automatic PSU switching](https://www.lcsc.com/datasheet/lcsc_datasheet_2304140030_Analog-Devices-LTC4412IS6-TRPBF_C521306.pdf), [Single Cell BMS](https://www.lcsc.com/datasheet/lcsc_datasheet_1912111437_TPOWER-TP4056_C382139.pdf) and a single [USB-C](https://www.lcsc.com/datasheet/lcsc_datasheet_1811151656_HOOYA-USB-310F-B-SU_C309365.pdf) for flashing and charging.
### Features
- 6-month battery life
- 4.2 inch 400x600 resolution [E-ink display](https://www.waveshare.com/4.2inch-e-paper-module.htm)
- Pre-ride weather updates (requires configuration)
- Board statistics display (Updates every 5 minutes)
- User Log (Requires Fingerprint Sensor)
> The InfoBar can only send/receive information to other devices on the ESPHome system. Do not attempt to integrate with your VESC-based speed controller as this will cause memory and pin allocation issues which will inevitably brick your VESC-based speed controller (The Odyssey Control Board is isolated for a reason)

> User log is stored inside Sensor memory. Your Biometric data will never be shared to or stored by other individuals without your consent. 

# Odyssey 3D Printing Guidelines
> If you aren't used to 3D printing or don't know where to start, I would recommend consulting an expert. Due to the dangerous nature of all self-balancing devices, 3D prints need to be strong, accurate and reliable.

Below, you can find the material recommendations and mechanical requirements for 3D prints for the Odyssey Self-balancing skateboard. 

## Minimum Specification
These are the absolute minimum requirements for 3D printing the Odyssey series 3D printed components. 
- Print Volume: 350mm x 350mm x 150mm 
- Material: [ABS](https://www.prusa3d.com/category/asa-abs/), [ASA](https://www.prusa3d.com/category/prusament-asa/), [PETG](https://www.prusa3d.com/category/prusament-petg/)
- Wall Thickness: 2-3x nozzle diameter
- Infill: >15%
> [How to make 3D prints waterproof](https://all3dp.com/2/waterproof-3d-print-pla/)
## Recommended Specification
- Material: [PC-CF](https://www.prusa3d.com/product/prusament-pc-blend-jet-black-970g/), [PA (Nylon)](https://www.prusa3d.com/category/prusament-pa-nylon/)
- [Support Material](https://dddrop.com/3d-printing-with-support-material/) (Ideally [Water Soluble](https://www.stratasys.com/en/materials/materials-catalog/fdm-materials/fdm-support-materials/#:~:text=Soluble%20support%20is%20most%20effective,submerged%20in%20the%20dissolution%20tank.))
- Infill: >20% ([Honey Pattern](https://all3dp.com/2/get-cura-honeycomb-infill/))
> You are expected to find your own 3D printer that meets these requirements. If this is outside of your budget, consider a 3D printing service.

# Avalon Series Tools + Hardware
The **Avalon Series** requires a lot of tools and miscellaneous parts to assemble. Here is a list of the most important, but not all of the products required to assemble your board.

This section only covers the physical mounting hardware, for electronic parts, see individual components. 
> Tool & Part Links are listed in format: "Name: UK Distributor / US Distributor" where applicable.
> If you're planning on wet riding, ensure you choose parts resistant to corrosion. 

## Tools
- Pinecil V2 Soldering Iron: [Global](https://pine64.com/product/pinecil-smart-mini-portable-soldering-iron/)
- Wera Kraftform Standard: [UK](https://www.accu.co.uk/bitholding-tools/644674-05051274001) / [US](https://accu-components.com/us/bitholding-tools/644674-05051274001)
- T6 Torx Bit: [UK](https://www.accu.co.uk/drive-bits/636302-HDB-H-T6-HS) / [US](https://accu-components.com/us/drive-bits/636302-HDB-H-T6-HS)
- T10 Torx Bit: [UK](https://www.accu.co.uk/drive-bits/636288-HDB-H-T10-HS) / [US](https://accu-components.com/us/drive-bits/636288-HDB-H-T10-HS)
- T25 Torx Bit: [UK](https://www.accu.co.uk/drive-bits/636292-HDB-H-T25-HS) / [US](https://accu-components.com/us/drive-bits/636292-HDB-H-T25-HS)
> If you're working on a budget, a precision screwdriver set can be a good idea. 
## Parts
- M2 x 6mm T6 Torx Pan Head Screws: [UK](https://www.accu.co.uk/hexalobular-pan-head-screws/475310-SHP-M2-6-V2-A4) / [US](https://accu-components.com/us/hexalobular-pan-head-screws/475310-SHP-M2-6-V2-A4)
- M2 x 3mm x 3.5mm: [UK](https://amzn.eu/d/bMJwggv) / [US](https://a.co/d/7rllooY)
 - M3 x 8mm T10 Torx Countersunk Screws: [UK](https://www.accu.co.uk/metric-torx-countersunk-screws/474332-SHK-M3-8-V2-A4) / [US](https://accu-components.com/us/metric-torx-countersunk-screws/474680-SHK-M3-8-V2-A4-BL)
 - M3 x 4mm x 5mm Brass Inserts: [UK](https://amzn.eu/d/eGp4Ldr) / [US](https://a.co/d/0UTHYOB)
 - M5 x 16mm T25 Torx Countersunk Screws: [UK](https://www.accu.co.uk/metric-torx-countersunk-screws/474743-SHK-M5-16-V2-A4-BL) / [US](https://accu-components.com/us/metric-torx-countersunk-screws/474744-SHK-M5-16-V2-A4-BL)
 - M5 x 8mm L x 7mm Brass Inserts: [UK](https://amzn.eu/d/6vIgD88) / [US](https://a.co/d/f2SdH9I)

> The websites listed are wholesalers due to the large number of duplicate parts. If you haven't used a wholesaler before, try and aim for the lowest price break so you have spares and save money. 

