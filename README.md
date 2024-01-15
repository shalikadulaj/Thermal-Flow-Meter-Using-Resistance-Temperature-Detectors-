# Thermal Flow Meter Using Resistance Temperature Detectors

## Electronic Sensors 521124S- 3006

**_Abstract – The project aimed to develop and optimize the parameters to reach the desired level of nonlinearity, a COMSOL model of a thermal flow meter for ethanol. Analog-to-digital converter and voltage amplifier were designed to convert sensor signals to voltage._**

**_Keywords—RTD, Flow sensor, Signal conditioner, ADC, COMSOL_**

### I. MEASURING VOLUMETRIC FLOW

Volumetric flow rate is the volume of a material flowing across a specific plane in a unit of time.

Volumetric flow rate:
```
Λ =V/Δt = ∫ v dA
```
Where v is the velocity of the medium, V is the displacement of volume and A is the cross-sectional area. Across the cross-sectional area, the velocity of the liquid can vary, and because of that average velocity should be taken.

The average velocity:

```
𝑣a= ∫v dA/A
```
Flow rate:

```
A𝑣a = ∫ v dA
```
When the cross-sectional area of the pipe is known, the average velocity can be measured using a sensor, and the flow rate can then be calculated. To measure the ethanol flow rate, a thermal transport flowmeter is used. This device detects the rate of heat dissipation in a flowing medium and is particularly effective for measuring very low flow rates. In this project, a heater is placed between two temperature sensors. As the flow increases, the downstream sensor records a higher temperature compared to the upstream sensor. When the individual responses of the sensors, are nonlinear. But the average temperature is quite linear. To measure the temperature RTDs (resistance temperature detectors) are used. The RTD sensor increases linearly with rising temperature. Since an RTD is a passive device and doesn't generate a signal on its own. Because of that a signal conditioner circuit is designed.

### II. COMSOL MODEL

A reference COMSOL Multiphysics model of a Thermo anemometer is provided, and the objective is to optimize it according to specified requirements.


  ![Geometry of the optimized COMSOL model](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/c71c3fce-afd0-463f-bf09-100fa6229ada)


Figure 1 Geometry of the optimized COMSOL model







The model consists of a solid pipe representing the flow path for the Ethanol. On the right side of the pipe, there are two sensors with a heater in between. Temperature sensors are represented by the upper and lower squares and the heater is represented by the middle square. Ethanol flows downward, with the inlet at the top and the outlet at the bottom. The upper sensor serves as a reference, while the lower sensor is affected by the heater.

Table 1 Parameters used in the model


![15 01 2024_02 00 42_REC](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/3a295f06-b7bb-47f7-84bc-69d82a31c748)







In this model, the cross-sectional area of the pipe, sensor position, heater position, and the velocity of the ethanol flow can be controlled. Simulation involves sweeping the velocity values, starting from 0. 00001 mm/s due to model limitations. The pipe width is 3mm and the thickness is 2mm.

The cross-sectional area of the pipe:

```
A = 3 mm ∗ 2 mm = 6 mm^2
```

Table 2 Given specifications



![15 01 2024_02 00 22_REC](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/d6f1b601-702b-40af-ad7c-65c89c1de5f9)




The maximum velocity is determined based on the maximum flow rate (0.5 μl/s) in specifications.

Maximum velocity:

```
Vmax =(0. 5 mm^3 /s)/6 mm^2 = 0. 0833 mm/s
```
This study focuses on ethanol as a liquid. Key parameters are viscosity (1.2 mPa*s) and density (0.789 g/ml) at 25 degrees Celsius. Temperature limits for ethanol are its melting and boiling points. Simulation yields sensor temperatures at various velocities, subsequently converted to resistances.

### III. SIMULATION RESULTS

1) Temperature distribution maps
Temperature maps for minimum and maximum flow are in the below figures. Higher flow increases heat dissipation and lowers maximum temperature. Changes in sensor temperatures are not very noticeable in the figures. Microsoft Excel was used for plotting and calculating parameters.


![Temperature distribution map for minimal flow](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/389068d1-c7aa-4f57-b278-9ff3fc53e384)




Figure 2 Temperature distribution map for minimal flow



![Temperature distribution map for maximal flow](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/ad88a677-3b27-447f-87e5-86923c9f69e2)



Figure 3 Temperature distribution map for maximal flow

2) Plots of temperatures of the sensors

The below graphs represent the reference sensor temperatures, downstream sensor temperatures, and average temperatures with respect to the inlet flow.



![Reference sensor temperature as a function of inlet velocity](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/f03b961c-55db-4b76-acc8-745301515c78)


Figure 4 Reference sensor temperature as a function of inlet velocity



![Downstream sensor temperature as a function of inlet velocity](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/78094dee-c13d-48f4-bec9-04114a174136)



Figure 5 Downstream sensor temperature as a function of inlet velocity


Both temperature sensor graphs are nonlinear, but the graph of average of the temperature is almost linear.



![Average of sensor temperatures as a function of inlet velocity](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/f55c623b-a6be-4003-ba48-f7b7aaa2d938)



Figure 6 Average of sensor temperatures as a function of inlet velocity

3) Nonlinearity calculation
From the average temperature graph, a trendline can be taken.

Trendline:

```
y = − 14. 638 x + 286. 75
```
This is linear. From this value for y, for every x can be calculated. The difference between the y value of the ideal response and the average plot is highest at the smallest x value 1E- 5. At smallest x the average temperature is 286.73 K.

Calculate 𝑥′:

```
𝑥′ = (y - 286. 75 K)/(-14.368) = (286. 73 K - 286. 75 K)/(-14.368) = 0.0010750
```
The maximum deviation:

```
0.001 0750 – 0.000010 = 0.0010650 
```
To normalize maximum deviation with flow, it is required to multiply it by the cross-sectional area.

Maximum deviation of flow:

```
0. 0010650 𝑚𝑚/𝑠 ∗ 6 mm^2 = 0. 006390 mm^3 /s
```
Maximum flow is 0. 49206 mm^3 /s at x value of 0. 08201 mm/s.

Nonlinearity:

```
0. 006390 𝑚𝑚^3 /𝑠 / 0. 49206 𝑚𝑚^3 /𝑠 * 100 % = 1. 2987 % ≈ 1. 3 %
```
 

According to the specifications maximum allowed nonlinearity is 5%. It is achieved. Optimization involved decreasing heater power to prevent ethanol temperature from reaching the boiling point and slightly adjusting the distances of the sensors from the heater. To minimize the nonlinearity at minimal flow was achieved by placing sensors at equal distances from the heater.

### IV. RTD SENSOR


In the model, the PTS0603M RTD sensor is used to convert the temperature into resistances.


![Technical specifications of PTS0603M RTD sensor](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/46ee932c-6d28-4755-8bfa-3070b84eec3c)


Figure 7 Technical specifications of PTS0603M RTD sensor

![15 01 2024_02 03 38_REC](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/90efbb93-7a08-4fbc-bf07-3648cf9a85c8)




Figure 8 Functional performance of PTS0603M RTD sensor

Specifications show the temperature resistance relationships of the PTS0603M RTS sensor. In this application, the temperature range is between 0 °C – 175 °C. Relevant equations can be used to compute the resistance at a given temperature.

Table 3 Resistance Values


![15 01 2024_02 01 01_REC](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/0db8e27f-bf23-4cf5-b453-73f611de425b)




### V. SIGNAL CONDITIONER CIRCUIT

The requirement is the ADC input voltage range 0 - 1V. According to the sensor specifications maximum current through the sensor is 0.5 mA. The below figures show the circuit for the downstream sensor and the reference sensor with the minimum and maximum resistors.


![Referance  Min](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/c2e8ed5f-1edc-4ea9-8b67-864acab3853c)




Figure 9 Reference sensor circuit with the minimal output value

![ReferanceMax](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/76d0295b-5580-4274-823f-b1d40966862b)



Figure 10 Reference sensor circuit with the maximal output value

![Downstream min](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/c03a57e8-85a1-4719-bafe-8be83445e678)


Figure 11 Downstream sensor circuit with the minimal output value


![Downstream max](https://github.com/shalikadulaj/Thermal-Flow-Meter-Using-Resistance-Temperature-Detectors-/assets/58818511/88768a3b-3972-475f-9a54-b2860c82ffb4)



Figure 12 Downstream sensor circuit with the maximal output value

The Wheatstone bridge comprises the sensor resistor R3 and three 1 0 5 Ω resistors. The 1 0 5 Ω value is close to the sensor resistance values at the minimal flow, ensuring the Wheatstone bridge is balanced. Consequently, the circuit's output is close to 0 V, even with a high gain from the last amplifier U2. In the reference sensor circuit, an inverting amplifier is used instead of non-inverting because the resistance decreases with increasing flow. And finally, output ranges cover over 77 % of the specification range from 0 V to 1 V.

### VI. REFERENCES


[1] Jacob Fraden, “Handbook of Modern Sensors”, 5th edition

[2] "VISHAY," [Online]. Available: https://www.vishay.com/docs/28899/ptsat.pdf.


