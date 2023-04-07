# Synthesizer design

Plan for a computer controlled analog polysynth. This project is in very early steps.  
The design is ~~mostly stolen from~~ slightly inspired by the Prophet-5 synthesizer. Of all the fields involved, analog circuitry is the one I'm least experienced with, so this borrows from designs made by other people.

The plan is to design a voice unit that be commanded by a Raspberry Pi, or such. The self contained design should make it easy to make changes to the voice unit or control without having to consider the other side too much.

Notable credits and resources:
- Great explanation on the 3340 VCO: https://electricdruid.net/cem3340-vco-voltage-controlled-oscillator-designs/
- I borrowed some resistor values for a 12 V design from here: https://www.skullandcircuits.com/the-oscillator-one/?v=d3dcf429c679
- https://cabintechglobal.com/tune3340

## Voice unit design:
Mostly following the Prophet-5 design. I'm planning to implement, envelopes, and such programmatically in the microcontroller. The only input to the module would be the I2C bus. VCO A uses pulse and saw outputs. VCO B uses the tri output as well. Uses 16-pin eurorack power connector. Maybe I can even repurpose the unused gate/CV pins for i2C?

![image](https://user-images.githubusercontent.com/100710152/227769749-eb6fe233-c4a6-49b9-8450-fe2f2020045d.png)

VCOs are built around AS3340, which is mostly compatible with CEM3340, but a lot cheaper. I used this for my monosynth, so I know I can at least build some kind of circuit that makes noise. The filter is built around AS3320.


![image](https://user-images.githubusercontent.com/100710152/227748842-793e98be-8b76-4fa4-a18e-6e5ff58b2f98.png)
