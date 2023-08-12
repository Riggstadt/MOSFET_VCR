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
