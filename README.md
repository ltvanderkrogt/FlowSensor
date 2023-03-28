# FlowSensor Hall YF-B10 (YF-B1, YF-B2, YF-B3)
<img src="https://user-images.githubusercontent.com/22962761/227800415-23c39647-59c9-4e5a-aeb2-49695b94c130.png" width=50% height=50%>

## Specification:<BR>
Function: Sensor, flow control<BR>
Thread size: Male 1"<BR>
Size: 58mm L<BR>
Color: Gold color<BR>
Flow Rate:2~50L/min<BR>
Flow Pulse: (6 * Q-8) Q = L/Min ± 5%<BR>
max. Working Current: 15mA (DC5V)<BR>
Min. Operating: DC 5V<BR>
Working voltage: DC7v-24v<BR>
Charging power: = 10 mA (DC 5 V)<BR>
Operational Working Temperature: -25 degrees celsius to +60 degrees celsius <BR>
Liquid Temperature: 60<BR>
Accuracy: 5% ~ 10%<BR>
Pressure: > 1.75MPa<BR>

## wiring Wemos D1 
  
The pins D5, D6, D7 work without restrictions<BR>
D3 and D4 work, but can not be low on boot, otherwise the WEMOS freezes<BR>
D1 and D2 are used for I²C by default, not changed for compability<BR>
D04 and D85 have no support for interrupts<BR>

Red = 5V<BR>
Yellow = PIN D5<BR>
Black = GND <BR>

## Calibration table;<BR>
<img src="https://user-images.githubusercontent.com/22962761/227793825-2f77f0cd-0c0f-4593-92d3-7e653d62471d.png" width=50% height=50%>
  I used this meter for calibration. Below 2 liter/minute it is not reliable anymore. <BR>
<img src="https://user-images.githubusercontent.com/22962761/228352849-9684f77f-642e-47b4-8d5d-841d8826be43.png" width=25% height=25%>


Output; <BR>
Flow rate: 21.76 L/min<BR>
<img src="https://user-images.githubusercontent.com/22962761/227914313-4c7c2146-8899-48ad-82be-d5e264e2a416.JPG" width=50% height=50%>
