# Experimental extraction of relevant MOSFET parameters 

We require for drain-to-source resistance calculations and for MOSFET calculations in general an accurate characterisation of MOSFET parameters.
## Theoretical determination and experimental approximation of parameters
At a purely theoretical level $I_{D}$ will be a function of two variables: $V_{GS}$ and $V_{DS}$. We take for example $R_{DS}$ in the Triode Region.

To determine its formula and value we need to take the partial derivative of $I_{D}$ with respect to $V_{DS}$ and voila. But there's a problem, we can't take the derivative when measuring currents and voltages with a multimeter. 

So instead of taking the derivative we will be calculating the slope of the curve, as we assume the IV characteristic of the FET to be mostly linear. After all, should we take two point infinitesimally close to each other, the resulting slope would have the same value as the derivative.

Note that for the parameter extraction we'll be doing, the selected transistor will be an IRF830.
## Measuring $V_{T}$
Finding $V_{T}$ shouldn't be too complicated. My main concern is that at the supply voltages being provided to the FET, the current through the Drain will be far too large and a small-value resistor shunt will get fried.

My challenges:
- Only 9V-ish batteries as power sources
- Ampmeter rated only for currents below 400mA
- No High Wattage Small Resistance power resistors or specialized current sensing shunts
- Avoid increasing $V_{GS}$ too much and conducting too much current and depleting the battery too quickly

My solution:
- I will use two 1W 3.3V zener diodes to limit $V_{DS}$ and act a sort of current sensor (explained below).
- I will use a 5.6V or 5.1V zener diode and a 50K potentiometer to ensure that the maximum current will be roughly below 1A

Explaining in detail the solution:
The zener diode maintains its breakdown voltage when the current is near or above its knee current $I_{ZK}$, which for the common 1W diodes I'll be using is somewhere between 250 $\mu A$ and 1000 $\mu A$. When the FET starts conducting the current through the diodes increases exponentially, turning them immediately on and lowering the voltage drop on the FET. So we roughly get the treshold voltage, but we also limit the current.

The gate will never be higher than 5-5.5V and the current shouldn't exceed 1A during normal operations. The zeners have a power rating of 1W, bigger than that of the 1N4148s that I have, so they are a better choice because of the currents involved.
