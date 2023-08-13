# MOSFET-based Voltage Controlled Resistor
MOSFETs are a type of Field Effect Transistors (FETs) frequently used for load switching and signal amplification. 
Besides the aforementioned use cases, there exists a third possible use case: Voltage Controlled Resistors (VCRs). 
This use case requires driving the FET into the deep triode region.

VCRs can be useful on their own, as part of voltage dividers, but their usefulness can be greatly enhanced by using them to craft Amplifiers with Voltage Controlled Gain.
## MOSFET CHARACTERISTICS
![image](https://github.com/Riggstadt/MOSFET_VCR/assets/127757267/e0c75924-6b7c-456c-9084-384cf711055f)

$$\begin{cases}
I_{D}=\frac{1}{2}\mu_{n}C_{ox}\frac{W}{L}\cdot \left[2\(V_{GS}-V_{T}\)V_{DS}-V_{DS}^{2}\right]\quad\text{for}\quad V_{GS}>V_{T}\quad\text{and}\quad V_{DS}\leq V_{GS}-V_{T}\\
\\
I_{D}=\frac{1}{2}\mu_{n}C_{ox}\frac{W}{L}\cdot \left(V_{GS}-V_{T}\right)^{2}\cdot \(1+\lambda V_{DS}\)\quad\text{for}\quad V_{GS}>V_{T}\quad\text{and}\quad V_{DS}\geq V_{GS}-V_{T}\\
\end{cases}$$

We are mainly interested in the large signal model of the FET in the triode region. As we approach the transition region between linear and saturation regions we encounter more and more non-linearities. At very low voltages, way below pinchoff voltage we enter the deep triode region and the nonlinearities present at highter voltages can be neglected as we simulate the FET as a voltage controlled resistor.

So, for $V_{DS} << 2\cdot\left(V_{GS}-V_{T}\right)$ we get $I_{D}=\mu C_{ox}\frac{W}{L}\left(V_{GS}-V_{T}\right)V_{DS}$. For higher sub-pinchoff voltages we get more non linear terms and have to contend with a more complex characteristic equation: $I_{D}=\mu C_{ox}\frac{W}{L}\left[\left(V_{GS}-V_{T}\right)V_{DS}-\frac{V_{DS}^{2}}{2}\right]$.

The formula for the drain-to-source resistance ($R_{DS}$), when the transistor is driven into the **deep triode** region, is derived as follows:
$$\frac{1}{R_{DS}}=\frac{\partial I_{D}}{\partial V_{DS}}=\frac{\partial \mu C_{ox}\frac{W}{L}\cdot\left(V_{GS}-V_{T}\right)\cdot V_{DS}}{\partial V_{DS}}=\mu C_{ox}\frac{W}{L}\cdot\left(V_{GS}-V_{T}\right)$$

So, $R_{DS}$ is equal to $\frac{1}{\mu C_{ox}\frac{W}{L}\cdot\left(V_{GS}-V_{T}\right)}$ for very low $V_{DS}$.

The MOSFET is now akin to a variable resistor, controlled by $V_{GS}$.
[imagine rezistor variabil si MOSFET]

We also introduce the notion of $R_{DS(on)}$, the drain-to-source resistance of the FET when $V_{GS}$ is equal to zero, which is also the minimum on resistance of the device. So for any particular $V_{GS}$ we can use this formula:
$$R_{DS}$$

Small-signal model for VCR
If we desire to use the MOSFET for small-signal AC applications we must take into account that for a given excursion $v_{ds}$ around the bias point of the FET we get: $v_{DS} = V_{DS} + v_{ds}$, where $v_{ds}$ is the applied AC signal at the FET's Drain. We are practically using the superposition principle and overlaying the large- and small-signal models of the FET in order to precisely simulate the operational behaviour.

If there are no AC variations in the gate-to-source voltage, the overall drain current equations reduces to this form: $i_{D}=I_{D}+i_{d}=I_{D}+g_{ds}\cdot v_{ds}= I_{D}+\frac{\partial I_{D}}{V_{DS}}\cdot v_{ds}$, where $\frac{\partial I_{D}}{V_{DS}}$ is equal unsurprisingly to $\mu C_{ox}\frac{W}{L}\left(V_{DS}-V_{T}\right)$.

After all is said and done, the overarching equation for the FET when biased in the deep triode region and supplied at its drain with a small AC signal is this:
$$i_{D}=\mu C_{ox}\frac{W}{L}\left(V_{DS}-V_{T}\right)\cdot\left(V_{DS}+v_{ds}\right)$$.

Large Signal Model for FETs
https://www.tina.com/resources/home/field-effect-transistor-amplifiers-2/2-metal-oxide-semiconductor-fet-mosfet/

Derivation of small signal model for FETs
https://inst.eecs.berkeley.edu//~ee105/fa98/lectures_fall_98/091898_lecture11.pdf

How the calculus works
https://electronics.stackexchange.com/questions/179592/small-signal-models-of-mos-amplifiers

More in-depth material
https://services.montefiore.uliege.be/microelec/uploads/ELEN0037/Lectures/Lecture%202%20Revision%20MOSFET%20Operation%20and%20Modelling.pdf

Small-signal Triode Region
https://www.youtube.com/watch?app=desktop&v=x4m8GwOdHhk&ab_channel=techgurukula


## LINEARIZING MOSFET ON RESISTANCE
Up until now we've neglected the non-linear terms of the triode region FET model. There are circumstances in which this terms become important and can affect the ohmic characteristics of the transitor. To remedy this we seek to linearize the $R_{DS}$.

$$I_{D}=\frac{1}{2}\mu_{n}C_{ox}\frac{W}{L}\cdot \left[2\(V_{GS}-V_{T}\)V_{DS}-V_{DS}^{2}\right]$$
Taking the partial derivative w.r.t. $V_{DS}$ we obtain: $R_{DS}= \frac{1}{2}\mu_{n}C_{ox}\frac{W}{L}\cdot \left[2\(V_{GS}-V_{T}\)-2V_{DS}\right]$.
We need to get rid of 

## LINEAR GAIN CONTROLLED AMPLIFIER
## CONCLUSIONS
## SOURCES
Finite output resistance of MOSFET:
https://www.youtube.com/watch?v=cdZiwwAIOp4&ab_channel=MansoorKhan

MOSFET on state drain source resistance
https://www.allaboutcircuits.com/technical-articles/understanding-mosfet-on-state-drain-to-source-resistance/

JFET VCR app note
https://www.vishay.com/docs/70598/70598.pdf

Linear Gain Controlled Amplifier app note
https://www.onsemi.cn/pub/collateral/an-6603cn.pdf

On resistance linearization 
https://neurophysics.ucsd.edu/courses/physics_120/The%20Field%20Effect%20Transistor%20as%20a%20Voltage%20Controlled%20Resistor.pdf
