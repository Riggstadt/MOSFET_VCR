# Experimental extraction of relevant MOSFET parameters 

We require for drain-to-source resistance calculations and for MOSFET calculations in general an accurate characterisation of MOSFET parameters.
## Theoretical determination and experimental approximation of parameters
At a purely theoretical level $I_{D}$ will be a function of two variables: $V_{GS}$ and $V_{DS}$. We take for example $R_{DS}$ in the Triode Region.

To determine its formula and value we need to take the partial derivative of $I_{D}$ with respect to $V_{DS}$ and voila. But there's a problem, we can't take the derivative when measuring currents and voltages with a multimeter. 

So instead of taking the derivative we will be calculating the slope of the curve, as we assume the IV characteristic of the FET to be mostly linear. After all, should we take two point infinitesimally close to each other, the resulting slope would have the same value as the derivative.

Note that for the parameter extraction we'll be doing, the selected transistor will be an IRF830.
## Measuring $V_{T}$
Threshold voltage can be defined in many ways, it all depends on what "threshold" current we decide to set as a benchmark.

I attempted to determine the value of $V_{T}$ with the help of several distinct testing methods:
- Constant Current Method: Biasing the FET with a constant current $I_{D}$ = 250 $\mu A$ and measuring $V_{GS}$
- Linear Extrapolation in Saturation Region: Diode-connected FET is biased by a variable voltage source and the threshold voltage is subsequently graphically determined
- Extraction from characteristic FET equation

### The Constant Current Method
This method works by setting a current source to output a constant, voltage independent drain current $I_{D}$ = 250 $\mu A$ into the Drain, which is shorted to the Gate of the device.

The CCS was built from a JFET and a resistor, a combination also called "constant current diode", as it can be seen in the figure from above.
The output current of the source is dictated by the resistance, which for a desired current $I_{D}$ has this formula: $R_{S}=\frac{V_{GS(off)}\cdot\left(1-\sqrt{\frac{I_{D}}{I_{DSS}}}\right)}{I_{D}}$. On the bench the fixed resistor was supplanted by a potentiometer to avoid having to extract the values of $I_{DSS}$ and $V_{GS(off)}$ for the specific transistor in use.

In our specific example the potentiometer was set to 2.922 $K\Omega$ and $I_{D}$ reached 255.6 $\mu A$, giving us the value of the threshold voltage as $V_{T}$ = 2.97V.

#### Notes on alternative arrangements for a CCS
An active device is not always required for this method, as a quicker, bench-friendlier method is to just measure $V_{GS}$ when the FET is supplied through a 0.1/1/10 $M\Omega$ resistor and the current is closer to another industry-standard current benchmark: $I_{test}=100 nA\cdot \frac{W}{L}$

### Linear Extrapolation in Saturation Region
This method necessitates the use of a diode-connected MOSFET and a variable supply voltage. Whilst performing the measurement and calculations, we must acknowledge that above the threshold voltage the FET is saturated because: $V_{GS}=V_{DS}$, $V_{GS}-V_{T} = V_{DS}-V_{T} < V_{DS}$
While varying the gate voltage we monitor the increase in current. After we gather all the data we graph $I_{D}$ vs $V_{GS}$. 
We can observe two distinct regions in the graph, above the threshold and below threshold (subthreshold region). In the above-threshold region the characteristic equation for the FET is valid, whilst in the subthreshold region the current ceases to obey the usual characteristic equations. We come up with another proper formula for the variation of $I_{D}$ in terms of $V_{GS}$ and $V_{DS}$:
$$I_{D}=I_{S}\cdot e^{\frac{V_{GS}}{\zeta U_{t}}}\cdot\left(1-e^{-\frac{V_{DS}}{\zeta U_{t}}}\right)$$
For $V_{DS}>4\cdot U_{t}$ the formula simplifies to: $I_{D}=I_{S}\cdot e^{\frac{V_{GS}}{\zeta U_{t}}}$. In our test circuit $V_{DS}$ and $V_{GS}$ will be equal.
### Extraction from characteristic FET equation
  
