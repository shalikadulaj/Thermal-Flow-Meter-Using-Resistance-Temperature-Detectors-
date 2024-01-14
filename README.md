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
When the cross-sectional area of the pipe is known, the average velocity can be measured using a sensor, and the flow rate can then be calculated.

To measure the ethanol flow rate, a thermal transport flowmeter is used. This device detects the rate of heat dissipation in a flowing medium and is particularly effective for measuring very low flow rates.

In this project a heater is placed between two temperature sensors. As the flow increases, the downstream sensor records a higher temperature compared to the upstream sensor. When gets the individual responses of the sensors, they are nonlinear. But the average temperature is quite linear.

To measure the temperature RTDs (resistance temperature detectors) are used. The RTD sensor increases linearly with rising temperature. Since an RTD is a passive device and doesn't generate a signal on its own. Because of that a signal conditioner circuit is designed.
