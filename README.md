# i_n_c_u_r

### a [r_e_c_u_r](https://github.com/cyberboy666/r_e_c_u_r) video sampler extension circuit - adding knobs, cv and serial midi control

![image](https://user-images.githubusercontent.com/12017938/151867823-2ffd7ad9-15bf-4f38-b4a9-118ac54efecb.png)

- this circuit is distributed by __UNDERSCORES__ - _an open video hardware label_ : it is available to purchase - as a pcb, kit or assembled unit - at [underscores.shop](https://underscores.shop/i_n_c_u_r/)
- the schematic for the circuit can be found [here](/hardware/schematic.pdf)
- the pcb gerber files for the lastest version can be found [here](/hardware/gerber_latest.zip)
- interactive BOM is [here](https://htmlpreview.github.io/?https://github.com/cyberboy666/i_n_c_u_r/blob/main/hardware/bom/ibom.html)
- consider [donating](https://opencollective.com/underscores) to the underscores project to help us continue creating for the commons

## description

__NOTE__ : _i_n_c_u_r_ is an extension circuit for my existing raspberry pi project [r_e_c_u_r](https://github.com/cyberboy666/r_e_c_u_r) - it will only be useful to you if you already have build a r_e_c_u_r

_disclaimer: this is a fun custom project, but dont forget there are other ways to getting serial and cv control over recur parameters. USB midi is supported in recur without any extra circuitry. other [diy](https://aemodular.boards.net/thread/141/simple-cv-midi-converter-arduino) and [commercial](https://www.befaco.org/en/vcmc/) products exist that convert cv to midi, and serial to USB. in my opinion a general solution for cv-to-usb-midi applied to recur is more useful than a specific board that only works with recur_

- 4x __knobs__ for physical control over shader parameters
- 4x __cv jacks (0-5v)__ for sequenced control over shader parameters (from older/analog synths eg eurorack)
- __serial midi__ din5 jack for sequenced control over shader parameters (from older midi devices)
- exposes _rpi video output through rca jack_ (rather than the 3.5mm trrs jack on pi )
- mounting holes and front facing interface parts for easier racking / enclosure building
- interfacing with rpi through gpio leaving all usb jacks free

## demo videos

[![image](https://user-images.githubusercontent.com/12017938/155867434-a2ea9398-58d5-4c8e-8ebe-b9a845a329d8.png)](https://videos.scanlines.xyz/w/534XkPbbdpDNjTziM6pPNG)

[![image](https://user-images.githubusercontent.com/12017938/151878669-bfd9f65a-8660-4917-8029-e255410f0958.png)](https://youtu.be/ah2HY1fuv8w?t=638)

# documentation

this project is fully _open-source hardware_ - all the files required to build it are included in this repo for free. if you have the time and/or skill you can contribute back by collaborating on / testing new designs, improving these docs, making demo videos/other creative content etc. you can also support the project financially by [donating directing](https://opencollective.com/underscores), or purchasing through the [web shop](https://underscores.shop).

depending on whether you are going fully diy or buying an assembled and tested unit, some of the following guides will be relavent to you. the flow would be:

## ordering parts

<details><summary><b>parts sourcing guide (w/ notes on pcb fabracation )</b> - start here if you are building fully from scatch or have purchased a pcb</summary>

i try to source all the parts i can from either:
- [tayda](https://www.taydaelectronics.com/) ; cheaper for common parts like resistors etc, also good for mechanical parts like switches and buttons
- [mouser](https://www.mouser.de/) ; has lots more options, speciality video ic's, can sometimes cost more (free shipping on orders over 50euros)
- other ; ocationally there will be parts which will need to be sourced elsewhere - usaully either aliexpress, ebay or amazon etc...

take a look at the [full_bom](/hardware/bom/full_bom.csv) for this project to see where i am sourcing each part from

## import into tayda

- go to the [tayda quick order](https://www.taydaelectronics.com/quick-order/) and in bottom corner choose _add from file_
- select the file [tayda_bom.csv](../hardware/bom/tayda_bom.csv) in the BOM folder (you will have to download it first or clone this repo)
- after importing select _add to cart_
- __NOTE:__ the minimum value for resistors is 10, so you may need to modify these values to add to cart (or if they are already modified here you will need to see the  full_bom for actual part QTY) 

- OPTIONAL: it is a good idea to add some dip-ic sockets and 2.54pin headers/sockets to your tayda order if you dont have them around already
  
## import into mouser

- go to [mouser bom tool](https://nz.mouser.com/Bom/) and click _upload spreadsheet_
- select the file [mouser_bom.csv](../hardware/bom/mouser_bom.csv) in this folder (you will have to download it first or clone this repo), then _upload my spreadsheet_ and _next_
- ensure that __Mouser Part Number__ is selected in the dropdown above the first row, then _next_, _process_
- if everything looks correct can now put _add to basket_

# ordering pcbs

you can support this project by buying individual pcbs from the [shop](https://underscores.shop). if you would rather have pcbs fabricated from gerbers directly the file you need is [here](/hardware/gerber_latest.zip) 

- i get my pcbs fabricated from [jlcpcb](https://cart.jlcpcb.com/quote) - 5 is the minumum order per design
- upload the zip file with the `add gerber file` button
- the default settings are mostly fine - set the __PCB Qty__ and __PCB Color__ settings (you can check that the file looks correct with pcb veiwer)
- it may be best to combine orders with other pcbs you want to have fab'd since the shipping can cost more than the items - also orginising group buys is a good way to distribute the extra pcbs /costs 
  
i often use jlcpcb because they are reliable, cheap and give you an option of colours. remember though that the cheapest Chinese fab houses are not always the most ethical or environmently friendly - if you can afford it consider supporting local companies. 

</details>

## assembly guide

<details><summary><b>assembly guide</b> - start here if you have purchased a diy kit</summary>
  

## interactive BOM for build guiding

follow this link to view the [interactive BOM](https://htmlpreview.github.io/?https://github.com/cyberboy666/i_n_c_u_r/blob/main/hardware/bom/ibom.html)

## general solder advices

- remember to heat pad first (2-3seconds), then add solder, then continue to heat (1-2seconds)

- Checkout the web-comic [soldering is easy](https://mightyohm.com/files/soldercomic/FullSolderComic_EN.pdf) for more soldering advice

## general order of assembly

- in general while assembling i start placing resistors and capacitors first. placing 5 - 10 components at a time and then flipping the board to solder them and trim the legs etc.
- next i would do diodes, transistors and ic's - taking care that these are placed in the right direction (using a ic socket can be useful)
- finally i place the interface parts - rca jacks, power jack, pots and switches - make sure these have lots of solder on for structural stablity

## slightly more specific assembly advice

start with the lowest to place components : resistors, diodes, ic's

next i would place the two headers since soldering from the top can be awkward with too many components - __NOTE these need to be placed upside down!__ ,:

- J8 needs the pins facing up from top of pcb so the screen can go ontop and raspberry pi can go underneath
- J6 also needs to soldered from the top so a jumper from the pi board can be run to bottom of circuit

finally place the pots and jacks.
  
### rca video-out

if you want RCA video out from the pi on this pcb a jumper needs to be run from J6 to the composite video out on the raspberry pi board. on pi0 this is a labeled pin, however on pi3 you will need to solder directly to the board. i used a header-cable, cut one side to be soldered. The pin on pi3 is marked as PP24.

[picture coming soon]
  
</details>
  
## operating guide
  
<details><summary><b>operating guide</b> - start here if you have purchased an assembled unit</summary>

![image](https://user-images.githubusercontent.com/12017938/152460623-594553bc-bd70-41ab-b25c-0dcfacb6dc7d.png)

- to enable the analog inputs ( knobs & cv ) go to `user_input` folder in r_e_c_u_r's `_SETTINGS_` tab and toggle `ANALOG_INPUT`
- to enable serial midi input go to `user_input` folder in r_e_c_u_r's `_SETTINGS_` tab and toggle `MIDI_INPUT` to _serial_
  
for more info on operating r_e_c_u_r see this [guide](https://github.com/cyberboy666/r_e_c_u_r/wiki/operate_docs)

</details>

### more info

<details><summary><b>how the circuit works</b></summary>
  

                                                                                                                             
</details>

<details><summary><b>contributing guide</b></summary>
  
if you would like to contribute back to these projects in some way but dont know how the best thing (for now) would be to reach out to me directly ( tim@cyberboy666.com or @cyberboy666 on scanlines forum) - i will be happy to help
  
</details>

## community contributed enclosure designs:

- an [eurorack panel design](enclosure/i_n_c_u_r%20_%20eurorack_panel.stl) by [Simon Gorzelnik](https://www.instagram.com/shimon.jpg/)
- a [base enclosure](enclosure/INCUR%20enclosure%20base.stl) by [miles](mailto:milesjohnsonwashere@gmail.com)

## credits & more info


This circuit is distributed through UNDERSCORES – open video hardware label – visit [underscores.shop](https://underscores.shop) for more info

The pcb was designed using KICAD

Everything from gerbers, cad files, panels and documentation is freely available online and distributed under CC-BY-SA / open-source licenses – help us contribute to the commons !

Ask any questions or start discussions related to this project on the [scanlines.xyz](https://scanlines.xyz) forum – an online community space dedicated to diy av / electronic media art

You can contact me directly at tim (at) cyberboy666 (dot) com 
Please get in touch if you are interested in hosting a workshop !

![image](https://user-images.githubusercontent.com/12017938/152463166-0fea052b-1eed-4f63-a59d-55c360bfea76.png)


Thanks to Signal Culture for giving me the time and space to explore. to Bastien Lavaud for circuit advice, always. To Ben Caldwell for project advice. To everyone who has or will contribute ♥♥♥

