# PCBasPRO_0002_Cheap_FOC2VESC
The PCBasPRO_0002 is an 2*motor controller board in development based on a JLCPCB parts. Ready for VESC6 up to 100V/200A design with individual gate drivers for all three phases. It is powered by an STM32F405 CPU and BLE WT51822_S4AT Capable of running Field Oriented Control at high power/voltages.

## **NOTE: Ongoing updates on text description, PCB and Schematic**


### **Features**

-  100V/200A continuous rating (RAW recomendation 84V/16A )
-   22s Battery voltage rating (Safe for 6S to 21S LIP0/Lllon, Voltage spikes may not exceed 100V)
-   1.5mm clearance on 100V (IPC-2221B, table 6-1, 51-100V on B3).
-   3-phase FOC motor control
-   4-layer smd design with individual gate drivers for all three phases
-   Onboard IMU STM32F405  ( USB-C, CAN and BLE ready with WT51822_S4AT)
-   6mm trace for a copper rail (allow a increase of current)
-   12V for gate drivers, 5V for CAN and IMU, and 3.3V for CPU and op-amped current-sense amplification
-   Cheap components available for ordering at [JLCPCB](https://jlcpcb.com/) and [LCSC](https://www.lcsc.com/)
-   1 PCB is 100x50mm, 2 PCBs with easybreak (can be splitted later) is 100x100mm and can drive 2 Motors.
-   Easy to find 100x100mm heatsink with cheap price 
-   Price target arround  5-10 euro extra comparing with [nordstream3](https://github.com/nordstream3/FOC/blob/main/README.md) 
-  Smallest transient loops possible
-   Extra ports connector (no unconnected pins on uC)


### **Current limitations**

- Shunt resistor is 12W,  arround 245A max;
- RAW PCB trace of 6mm, arround 16A max @delta 40ºC
  - By apply solder past will [decrease the resistance in 50%](https://www.youtube.com/watch?v=L9q5vwCESEQ) so can go for 32A
  - By apply [5*3mm copper](https://pt.aliexpress.com/item/1005002120776637.html?spm=a2g0o.productlist.main.5.79f550abtxXGGP&algo_pvid=89dc8ee5-5a69-4b70-b033-81fb0f95cf3f&algo_exp_id=89dc8ee5-5a69-4b70-b033-81fb0f95cf3f-2&pdp_npi=4%40dis%21EUR%2131.46%2123.6%21%21%2134.17%21%21%402103010b17038034248783515ec46c%2112000032430582895%21sea%21PT%21181591003%21&curPageLogUid=vuNuAm37cAhX) [will add 190A](https://circuitcalculator.com/wordpress/2006/01/31/pcb-trace-width-calculator/)
  - Now if we consider the 3 parallel of the iqual resistors we will have 1/3 (something between 66%-50% not the 50% as before) so I expect more then 190A already!!! So go crazy!!!!
  - We can use this area to solder a [copper heatshink](https://pt.aliexpress.com/item/1005001757382767.html?spm=a2g0o.detail.0.0.3c9edHXJdHXJNr&mp=1&gatewayAdapt=glo2bra) to make 2 in 1
- 2 Connectors XT-90 100A*2=200A
- Mosfet 100V 268A@100ºC dont forget the [heatsink](https://pt.aliexpress.com/item/1005003852083731.html?spm=a2g0o.home.0.0.25901c91u1EahD&mp=1&gatewayAdapt=glo2bra) and the follow info:
![Image](https://github.com/PCBasPRO/PCBasPRO_0002_Cheap_FOC2VESC/blob/main/2023-12-28_23h52_00.png)
  

### **My next steps**

- Impedance match to stack-up
- Re-calculate all power and current, from footprint and traces point of view
- Evaluate ESP32...
- update PCB with privious topics.
- Evaluate the CAN connection to have a dual motor control in 100x100mm board (really cheap at JLCPCB)
- Get some people interested in Buy/testing the dual motor control (no good material at home for that)
- Start conversations with VESC tool or set firmware
- Pending from the selled test samples a case creations in aluminium


### **PCB Status**

TOP: 
![Image](https://github.com/PCBasPRO/PCBasPRO_0002_Cheap_FOC2VESC/blob/main/2023-12-28_15h43_59.png)
![Image](https://github.com/PCBasPRO/PCBasPRO_0002_Cheap_FOC2VESC/blob/main/2023-12-28_15h47_45.png)
Bottom:
![Image](https://github.com/PCBasPRO/PCBasPRO_0002_Cheap_FOC2VESC/blob/main/2023-12-28_15h44_15.png)
![Image](https://github.com/PCBasPRO/PCBasPRO_0002_Cheap_FOC2VESC/blob/main/2023-12-28_15h48_12.png)
### **Acknowledgements**

This PCB is a combination of some ideas/work of the follow projects:

- https://github.com/shamansystems/Cheap-FOCer-2
- https://github.com/nordstream3/FOC/blob/main/README.md
- https://forum.esk8.news/t/prototyping-high-power-vesc-6-4-variant/32036/66

### **Donate**

If you find this project useful and would like to support bread-and-butter for very time consuming development and maintenance, you can [donate](https://www.paypal.com/donate/?hosted_button_id=CDQSZKZBMZTBL)  to the creator via Paypal.
