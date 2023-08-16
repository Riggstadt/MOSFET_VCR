# Experimental extraction of relevant MOSFET parameters 

We require for drain-to-source resistance calculations and for MOSFET calculations in general an accurate characterisation of MOSFET parameters.
## Theoretical determination and experimental approximation of parameters
At a purely theoretical level $I_{D}$ will be a function of two variables: $V_{GS}$ and $V_{DS}$. We take for example $R_{DS}$ in the Triode Region.

To determine its formula and value we need to take the partial derivative of $I_{D}$ with respect to $V_{DS}$ and voila. But there's a problem, we can't take the derivative when measuring currents and voltages with a multimeter. 

So instead of taking the derivative we will be calculating the slope of the curve, as we assume the IV characteristic of the FET to be mostly linear. After all, should we take two point infinitesimally close to each other, the resulting slope would have the same value as the derivative.

Note that for the parameter extraction we'll be doing, the selected transistor will be an IRF830.
## Measuring $V_{T}$
There are sevral ways of finding out the treshold voltage, including the following:
- Shorting the Drain and the Gate together and sweeping $V_{DS} / V_{GS}$ until $I_{D}$ is 250 $\mu A$
- Still shorting the Drain and the Gate, but this time we take $V_{T}$ to be the the $V_{DS}$ at which the line between two saturated bias-points intersects the X-Axis of the IV chart.
- Taking $I_{D}$ and $V_{GS}$ for two given bias-points and doing some maths
- 
