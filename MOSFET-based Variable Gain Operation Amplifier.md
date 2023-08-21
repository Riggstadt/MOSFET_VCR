# TO DO
In the other one finish the extraction of lambda
Here I will build a simple non-inverting op-amp with the LM358p chips
formula for amplification referenced to both Rds = bla bla and Rdson and what not

first I test the formulas on potential divider at a low fixed VDS and see how close we get with our theoretical methods

and I also test where the linearity stops and the knee kicks in. How? I pass the low voltage ramp from the function generator to the drain at a fixed VGS > VT

# TO DO RAMP GENERATOR
- Build on perf board
- Replace PNP current source with JFET CCS
- Add low value resistor at drain
- Zener diode selection to minimize maximum VGS

Steps to follow:
- Test circuit for adequate ramp and range of values, lineariy even at VT and above [unloaded]
- as above [loaded]
- Current sense opamp circuit with JFET current source load
- combine those above and test

  https://mrevil.asvachin.com/electronics/modules/
  https://www.radiolocman.com/shem/schematics.html?di=599185
  https://electronics.stackexchange.com/questions/285733/why-do-these-precision-current-sinks-use-both-a-jfet-and-bjt-instead-of-one-fet
  https://www.analog.com/en/app-notes/an-105fa.html
  https://www.analog.com/en/technical-articles/micropower-precision-current-sense-amplifier-operates-2-5v-60v.html
