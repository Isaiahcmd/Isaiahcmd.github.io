---
title: Moisture Sensor Component Selection 
---


**Sensing and Probe Plate**

| **Solution**                                                                                                                                                                    | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
|![image](000951.png){width=70%}<br>Option 1.<br>* Type: Interdigitated Comb<br>Manufacturer: Peralta (made in house)<br> | \* High sensitivity area of plate<br>\* Good signal to noise ratio<br>\* Low draw allows continuous sensing  | \* High influence from air pockets<br>\* Salty soils can cause shorts. <br>\* Hard to clean.|
|  ![image](001209.png){width=70%}<br>\ Option 2. <br>\* Type: Parallel Plates<br>\* Manufacturer: Peralta (made in house) <br>\* Design use only | \* Easy to design and etch <br>\* Low cost <br> \* Low risk of shorting | * Low overall capacitance <br>\* Low range of measurement <br>\* Non-uniform sensing region|
|![image](004911.png){width=20% height=10%}![image](004859.png){ width=20% height=10%}<br>\(back and front of probe)<br> Option 3.<br>\* Type: Multi-layer<br>\* Manufacturer: Peralta (made in house)|* High sensitivity in bulk soil<br>\* Deep measurement<br>\* pairs can be chained to measure at different soil depths|* Higher manufacturing tolerances<br>\* Higher cost<br>\* Probe stiffness makes it susceptible to cracking|

**Choice:Interdigitated Comb**

**Rationale:** The interdigitated comb design has a larger excite and sensing region when compared to a paralel plate design of the same volume. The comb design is easier and cheaper to manucatur than the layered design due to its acceptable tolerence range.


  **Op-Amp Buffer**

| **Solution**                                                                                                                                                                    | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
|![image](212236.png){width=70%}<br>Option 1.<br>\* LM358P<br>\* Op-Amp buffer<br>\* $0.27/each<br>[Digikey](https://www.digikey.com/en/products/detail/texas-instruments/LM358P/277042) | \* Resilient under heat<br>\* Low cost<br>\* High surge current tolerance| \* Higher Vf can reduce efficiency in dry soil<br>\* High junction capacitance<br>\* Bulky|
| ![image](211521.png){width=70%}<br>\ Option 2. <br>\* CA3240EZ<br>\* Op-Amp buffer<br>\* $3.19/each<br>[Digikey](https://www.digikey.com/en/products/detail/renesas-electronics-corporation/CA3240EZ/821389) | \* Fast slew<br>\* Low input bias<br>\* Good bandwidth |* Not rail to rail I/O<br>\* Noticable drift with temperature<br>\* Input noise|
|![image](211619.png){width=70%}<br>\ Option 3.<br>\* MCP6022-I/P<br>\* Op-Amp buffer<br>\* $1.86/each<br>\*[Digikey](https://www.digikey.com/en/products/detail/microchip-technology/MCP6022-I-P/417828) |*Low input bias<br>\* Fast slew<br>\* Low offset|* Low drift with temperature rise<br>\*Small baseline drift<br>\*At risk of latchup potentially causing damage to the part|

**Choice: MCP6022-I/P**

**Rationale:** The MCP6022-I/P will be used for its low bias, and fast slew rate. Consuming minimal power and sending a clean signal.


| **Solution**                                                                                                                                                                    | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
|![image](150924.png){width=70%}<br>Option 1.<br>\* L7805CV<br>\* Linear Regulator<br>\* $0.50/each<br>[Digikey](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964) | \* Lowest cost<br>\* Low noise<br>\* No switching spikes| \* Energy inefficient<br>\* Generates heat which could throw readings or introduce condensation<br>\* Higher idle drain|
| ![image](151234.png){width=70%}<br>\ Option 2. <br>\* TSR 1-2450E<br>\* Switching Regulator<br>\* $3.40/each<br>[Digikey](https://www.digikey.com/en/products/detail/traco-power/TSR-1-2450E/12171283?s=N4IgTCBcDaICoCcCGBjA9gAjgZQEoFoBGfMAFgFYAGEAXQF8g) | \* Low heat<br>\* Energy efficient<br>\* Low idle draw |* Most expensive<br>\* Higher output ripple<br>\* Higher electromagnetic interference|
|![image](151435.png){width=70%}<br>\ Option 3.<br>\* LM2596S-5.0<br>\* Switching Regulator<br>\* $3.32/each<br>\*[Digikey](https://www.digikey.com/en/products/detail/umw/LM2596S-5-0/16705901) |*Good efficiency<br>\* Operates in a wide voltage range<br>\* High current headroom|* Noisier than other options<br>\* High Idle draw<br>\* Needs tuning/ Extra QA for productions runs|

**Choice:TSR 1-2450E**

**Rationale:** The TSR 1-2450E will be used for its efficiency in stepping down power while producing low heat, and stable output under load.

**Revision 1.1:** Due to the lack of support documentation for the TSR 1-2450E a change was made to the LM2575-5.0WT. The manufacturer, Microtech Technologies, provides goood recources on the exact way to build the circuit for a functioning voltage regulator.![image](120830.png){width=70%}

**Power Supply**

| **Solution**                                                                                                                                                                    | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
|![image](192016.png){width=70%}<br>Option 1.<br>\* 16-00030 AC/DC WALL MOUNT ADAPTER 12V 6W<br>\* Wall outlet power supply<br>\* $6.77/each<br>*[Digikey](https://www.digikey.com/en/products/detail/tensility-international-corp/16-00030/10324409?gclsrc=aw.ds&gad_source=1&gad_campaignid=20232005509&gbraid=0AAAAADrbLlhDPP3OBpG5nKxDHh9GweBbP&gclid=CjwKCAjw3tzHBhBREiwAlMJoUr_wV-gGGldVXDYFfLn7gjQ5H6BAUQ0fgq_vArBnfdnLXE7DjR_N5xoCaXwQAvD_BwE) | \*Lowest cost<br>\* Constant power<br>\* Clean supply| \* Not portable<br>\* Limited use without extension cords<br>\* Indoor use only|
| ![image](162602.png){width=70%}<br> Option 2. <br>\* RadioMaster 5000mAh 2S 7.4V Li-ion Battery with XT30 Connector<br>\* Rechargeable power supply<br>\* $25.99/each<br>[MotionRC](https://www.motionrc.com/products/radiomaster-5000mah-2s-7-4v-li-ion-battery-with-xt30-connector-hp0157-batt-5a2s?srsltid=AfmBOoouwp1tw2VWueXsnK8W4uQuzwqAE6nUhBdlDAyu8GNJax9JY2X0) | \* Long runtime<br>\* Compact<br>\* Easy connection |* Highest cost<br>\* Performance loss at freezing and high heat<br>\* Risk of over voltage spikes|
|![image](193501.png){width=70%}<br>\ Option 3.<br>\* 2440 BATT HOLDER AA 4 CELL 6" LEADS<br>\* Replacable power supply<br>\* $9.68/each<br>\*[Digikey](https://www.digikey.com/en/products/detail/keystone-electronics/2440/9561058?gclsrc=aw.ds&gad_source=1&gad_campaignid=20243136172&gbraid=0AAAAADrbLliKbEh2iWNss6PAqtweLuMmH&gclid=CjwKCAjw3tzHBhBREiwAlMJoUjfBbA3qv7wjORBrH5ku49U_r9DPOGB7L7E-aR4IS9pyWZ6hrcpbbhoCxeoQAvD_BwE) |*User can easily replace cells<br>\* Low cost to replace cells<br>\* Safer for users than a Li-ion battery|*Lower energy density<br>\* Not weather proof<br>\* More affected by weather than Li-ion|

**Choice: 16-00030 AC/DC WALL MOUNT ADAPTER 12V 6W**

**Rationale:** 16-00030 AC/DC WALL MOUNT ADAPTER 12V 6W, will be used for its convenience and easy of use.

**Revision 1.1:** The initial choice was abandoned for the class provided 237-1449-ND 9V power supply. This was done to save money. There was no obvious reason to chose another power supply.![image](120830.png){width=70%}

**Connector Header**

| **Solution**                                                                                                                                                                    | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
|![image](114105.png){width=70%)<br>Option 1.<br>\* TB002-500-02BE TERMINAL BLOCK, SCREW TYPE, 5.00<br>\* Wire connection<br>\* $0.40/each<br>[Digikey](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/TB002-500-02BE/10064069) | \* Least expensive<br>\* Flexible connections<br>\* Secure connection| \* Bulky<br>\* Slower assembly/Slow production<br>\* Screws can back off with vibration|
| ![image](115526.png){width=70%}<br>\ Option 2. <br>\* EBC04MMMD CONN CARDEDGE MALE 8POS 0.100<br>\* Board-to-board connection<br>\* $2.69/each<br>[Digikey]([http://EBC04MMMD-ND](https://www.digikey.com/en/products/detail/sullins-connector-solutions/EBC04MMMD/4538822?s=N4IgTCBcDaIKICEDCAGALAWSwEQARIHkA5I-AQQCVs5sBxOXDMgGQYA4AFAgZVxQDoAjChQgAugF8gA)) | \* Compact<br>\* Short signal path = good integrity<br>\* Makes board easily swapable |* No flexibility<br>\* Most expensive<br>\* Non Locking|
|![image](120830.png){width=70%}<br>\ Option 3.<br>\* 215570-8 CONN DIP HDR IDC 8POS 28AWG PCB<br>\* Ribbon connection<br>\* $0.81/each<br>\*[Digikey]([https://www.digikey.com/en/products/detail/stmicroelectronics/1N5817/770963](https://www.digikey.com/en/products/detail/te-connectivity-amp-connectors/215570-8/4142495)) |*Flexible connections<br>\* Fast attachment and detachment<br>\* Keyed to prevent incorrect plug in|* Not sealed<br>\* Limited current<br>\* No strain relief|

**Choice:215570-8 CONN DIP HDR IDC 8POS 28AWG PCBP**

**Rationale:** The 215570-8 CONN DIP HDR IDC 8POS 28AWG PCB will be used for flexibility, modularity, and ease of assembly of the ribbon connection.
**Future Revision** The initial choice was incorrect for the provided ribbon connector. A choice like the TSW-104-07-F-D would be more suited for the role.![image](120830.png){width=70%}
