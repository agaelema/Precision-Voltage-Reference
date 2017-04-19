# Precision Voltage Reference

A simple and efficient instrumentation project of a Precision Voltage Reference. The idea of this project appeared with my passion by the instrumentation and my need of some reference to calibrate my projects involving energy measurement. 

Searching for similar projects I encountered some videos from the Youtube channel "Scullcom Hobby Electronics". This two videos was the kick for my project.
- [Video 1](https://youtu.be/QnH5O-AhqAU?list=PLqnWlo4M8pvoofVfDM7LorucKpwpznr12)
- [Video 2](https://youtu.be/QnH5O-AhqAU?list=PLqnWlo4M8pvoofVfDM7LorucKpwpznr12)

The project is based in the [TI REF102](http://www.ti.com/product/REF102), an 10 V precision voltage reference with maximum tolerance of 0,025% (0.0025 V) in the better model.

Other 4 outputs are derived from the 10 V output, making available 10 V, 5V, 2,50V, 1,125 V and 0,625 V.  This values are obtained using the Precision Difference Amplifier [INA2133](http://www.ti.com/product/INA2133)

The original idea is to be a simple project with components easily found in the market.

### The Supply

The project is powered by a common 5V power bank, and the output of the power bank is applied to a DC/DC step up to 20 V. With one LM317 and one LM337 we generates the positive supply for the REF102 and negative voltage to compensate some offset in the INAs.

The output is referenced to a Virtual ground, not the GND from the power bank.

![alt text](https://www.embarcados.com.br/wp-content/uploads/2016/09/ref-supply-final-273x263.png "Linear power supply")

### The Outputs

Using the INA2133 is possible to implement a 1/2 divider with great precision. At the same time the outputs are buffered between the stages.

To compensate some possible input offset in the stages, was implements simple circuits to externally compensate the offset. This circuit inject some voltage in the Ref pin of the INA.

The ideia of divider:
![alt text](https://www.embarcados.com.br/wp-content/uploads/2016/08/ref-ina-offset-696x266.png "INA 1/2 Divider")

### The Result

The project was developed using Kicad. The [complet schematic](https://github.com/agaelema/Precision-Voltage-Reference/blob/master/ref-schematic-big.png) is presented bellow.

![alt text](https://github.com/agaelema/Precision-Voltage-Reference/blob/master/ref-schematic-big.png?raw=true "Schematic")

![alt text](https://github.com/agaelema/Precision-Voltage-Reference/blob/master/ref-board-3d_compressed.jpg?raw=true "Schematic")

The assembled board.

![alt text](https://www.embarcados.com.br/wp-content/uploads/2016/09/ref-board-373x263.jpg "Assembled board")

The results without calibration (default value), calibrating just the REF102 output and calibrating each output individually.

![alt text](https://www.embarcados.com.br/wp-content/uploads/2016/09/ref-dmm-result-696x313.jpg "Assembled board")

### Related Articles

There is a serie of 4 articles talking about this project.
- [Article 1 (The idea)](https://www.embarcados.com.br/referencia-de-tensao-de-precisao-a-ideia/)
- [Article 2 (The power supply)](https://www.embarcados.com.br/desenvolvendo-a-fonte-para-referencia-de-precisao/)
- [Article 3 (The voltage reference)](https://www.embarcados.com.br/referencia-de-tensao-da-referencia-de-precisao/)
- [Article 4 (The results)](https://www.embarcados.com.br/resultados-referencia-de-precisao/)