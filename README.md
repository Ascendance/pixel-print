# pixel-print
 
###### A library to print letters and numbers onto 5x8 LED matrices. (LiteON LTP-2058AG and LTP14058AG)

<b>Introduction</b>

This library prints letters and numbers onto 5x8 matrix in sequential order. <br />
With an Approx. 300 ms delay between each letter. 

<b>Requirements</b>

1. Texas Instruments SN74LS145 BCD-To-Decimal Decoder
2. Texas Instruments SN7404N Inverter
3. Resistor Arrays for LED's

<b>Process</b>
##### Step 1: Build your circuit :: Row control

+ Make sure outputs 0 to 7 from SN74LS145 are wired to SN7404N then into resistor array then into 5x8 matrix. 
+ We do this because we want only low outputs from the SN74LS145 IC.
- In order words we want to light up only the LED's we need
+ Outputs 0 to 7 from SN74LS145 controls the **rows** of the 5x8

##### Step 2: Build your circuit :: Column control

+ Wire the column control pins into resistor array then into your Raspberry Pi 2
- Column controls do not need inversion because it's easy to control using the Pi. 

##### Step 3: Print!

+ Initialize object using `led = pixelprint.LEDMatrixControl()`
+ Print using `led.matrixPrint("YOUR TEXT HERE")`

--

<b>Pixel-Print Pin Numbers</b>

| LiteON 5x8    | Raspberry GPIO|
| :------------:|:-------------:|
| Row 1         | Pin 5         |
| Row 2         | Pin 6         |
| Row 3         | Pin 13        |
| Row 4         | Pin 19        |
| Row 5         | Pin 26        |
| Column 1      | Pin 21        |
| Column 2      | Pin 10        |
| Column 3      | Pin 16        |
| Column 4      | Pin 12        |

<b>IC Datasheets</b>

+ SN74LS145 > http://www.ti.com/lit/ds/symlink/sn54ls145.pdf
+ SN7404N   > http://www.ti.com/lit/ds/symlink/sn74ls04.pdf

<b>LICENSE</b>
MIT. See LICENSE file for full details. 
