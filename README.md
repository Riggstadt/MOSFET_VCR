# MOSFET-based Voltage Controlled Resistor
MOSFETs are a type of Field Effect Transistors (FETs) frequently used for load switching and signal amplification. 
Besides the aforementioned use cases, there exists a third possible use case: Voltage Controlled Resistors (VCRs). 
This use case requires driving the FET into the deep triode region.

VCRs can be useful on their own, as part of voltage dividers, but their usefulness can be greatly enhanced by using them to craft Amplifiers with Voltage Controlled Gain.
## MOSFET CHARACTERISTICS
![image](https://github.com/Riggstadt/MOSFET_VCR/assets/127757267/e0c75924-6b7c-456c-9084-384cf711055f)

$$\begin{cases}
I_{D}=\frac{1}{2}\mu_{n}C_{ox}\frac{W}{L}\cdot \left[2\(V_{GS}-V_{T}\)V_{DS}-V_{DS}^{2}\right]\cdot \(1+\lambda V_{DS}\)\quad\text{for}\quad V_{GS}>V_{T}\quad\text{and}\quad V_{DS}\leq V_{GS}-V_{T}\\
\\
I_{D}=\frac{1}{2}\mu_{n}C_{ox}\frac{W}{L}\cdot \left(V_{GS}-V_{T}\right)^{2}\cdot \(1+\lambda V_{DS}\)\quad\text{for}\quad V_{GS}>V_{T}\quad\text{and}\quad V_{DS}\geq V_{GS}-V_{T}\\
\end{cases}$$


/****/
$I_{D}=f\left(V_{GS},V_{DS}\right)$
$I_{D}=G_{m}\cdot V_{GS} + G_{o}\cdot V_{DS}$
$G_{m}=\frac{\partial I_{D}}{\partial V_{GS}}$

Some thoughts on this:
I encountered some difficulties in understanding the difference between small signal and large signal models of the FET. I now firmly understand the differences and similarities between the two.

We are mainly interested in the large signal model of the FET in the triode region. As we approach the transition region between linear and saturation regions we encounter more and more non-linearities. At very low voltages, way below pinchoff voltage we enter the deep triode region and the nonlinearities present at highter voltages can be neglected as we simulate the FET as a voltage controlled resistor.
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
