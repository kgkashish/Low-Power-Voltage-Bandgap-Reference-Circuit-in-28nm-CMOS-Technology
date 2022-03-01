# Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology

# Table of Contents
- [Abstract](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/README.md#abstract)
- [Introduction](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/README.md#introduction)
- [Circuits and Waveforms](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/README.md#circuits-and-waveforms)
  1. [BGR design for low voltage](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/README.md#BGR)
  2. [BGR design with opamp and startup circuit](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/README.md#BGR_With_Opamp)
  3. [Simulation state](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/README.md#Simulation_Testbench_state)
  4. [Vref output waveform for varing temperature](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/README.md#Output_Waveform_of_BGR_voltage)
  5. [Vref output waveform for varying supply voltage](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/README.md#Output_Waveform_of_BGR_voltage)
- [Netlist](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/README.md#Netlist)
- [References](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/README.md#references)
- [Acknowledgements](https://github.com/laptopcomputermistri/Nikhil/blob/main/README.md#acknowledgements)
- [Author](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/README.md#author)

# Abstract
A low power CMOS bandgap reference (BGR) circuit with low temperature coefficient is to be designed. BGR is used in Low dropout regulators and other DC to DC converters to compare any signal with the constant reference voltage which is supplied by BGR. The conventional bandgap reference circuit typically produces an output voltage of 1.2v that prevents the low voltage operation. A T-structure bandgap is the core circuit being used to design such a circuit that is capable of operating at lower supply voltage that can also provide low temperature coefficient of reference voltage (V REF ). V REF is obtained from the sum of the two currents, one being proportional to V BE and the other proportional to V T. The proposed circuit consists of a CMOS opamp, BJTs and resistors and is designed in CMOS 28nm technology.

# INTRODUCTION
The conventional BGR circuits are not useful for low voltage operation because in that circuit V T increases linearly with temperature while V BE decreases approximately linearly with temperature. For generating low temperature dependent V REF, both V BE and V T are summed along with the temperature scaling (K) factor and we get V REF =1.2V, PTAT current generation loop is limited by the collector current structure of the BJT and the input common-mode voltage of the
amplifier. The technique used in this circuit lies in generating two currents; one proportional to V BE which is minimum due to R 2 & R 3 resistors and the other proportional to V T by only one feedback loop. In the proposed design the high gain operational amplifier with PMOS input differential pair is used to maintain equal node voltages and provide stable feedback to maintain the constant current that is independent of supply voltage variations. Stability of the OPAMP is
achieved by using compensation capacitor and nulling resistor. The current flowing through M P1 , M P2 and M P3 are the same and therefore PMOS transistors should be of the same dimensions so I 1 = I 2 = I 3 and V x =V y by using a high gain amplifier. In the proposed equivalent T-circuit in bandgap core for calculating I 2q which has positive temperature coefficient proportional to V BE and here I 3 is the sum of I 2q and I 2p . The negative temperature coefficient of current of the BGR circuit is reduced by big factor and then summed with positive temperature coefficient current resulting in low resistor value. Hence the overall voltage
value is less compared to the conventional BGR circuit and other low voltage BGR circuits.

# Circuits and Waveforms
## Low voltage BGR
![BGR circucit design](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/bgr_schematic_low_voltage.png)

## BGR With Opamp
![BGR design with Startup](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/bgr_with_opamp_schematic.png)

## Simulation Testbench state
![simulation state](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/simulation_state.png)

## Output Waveform of BGR voltage
![Vref output waveform for varying temperature](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/vref%20vs%20supply.png)

![Vref output waveform for varying supply voltage](https://github.com/kgkashish/Low-Power-Voltage-Bandgap-Reference-Circuit-in-28nm-CMOS-Technology/blob/main/vref%20vs%20temp.png)

# Netlist
```
*  Generated for: PrimeSim
*  Design library name: Kashish_analog_ic_design
*  Design cell name: Bgr_design_final
*  Design view name: schematic
.lib 'saed32nm.lib' TT
.lib 'saed32nm.lib' BJT

*Custom Compiler Version S-2021.09
*Tue Mar  1 09:37:22 2022

.global gnd!
********************************************************************************
* Library          : Kashish_analog_ic_design
* Cell             : Bgr_design_final
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xm28 net100 net100 gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm27 net103 net100 gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm25 net129 net94 gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm24 net94 net134 gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm23 net134 net134 gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm22 net133 net128 gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm17 net128 vref gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm16 net128 net128 gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm21 net134 net133 net63 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm20 net94 net121 net63 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm14 net103 net103 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm13 net129 net103 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm12 net63 net103 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm11 net133 net129 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm10 net100 net129 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm9 net121 net129 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm8 vref net129 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
q30 gnd_1 gnd_1 net111 vpnp area=4p m=2
q29 gnd_1 gnd_1 net133 vpnp area=4p m=1
q41 gnd_1 gnd_1 net143 vpnp area=4p m=1
r35 vref net143 r=10k
r34 net113 gnd_1 r=1k
r33 net133 net113 r=1k
r32 net113 net121 r=1k
r31 net121 net111 r=1k
r26 net96 net94 r=1k
r15 vdd net128 r=1k
c5 net96 net129 c=1f
v38 gnd_1 gnd! dc=0.8
v40 vdd gnd! dc=0.8
v39 vdd_1 gnd! dc=0 pulse ( 0 1.8 100u 100u 100u 0.5 1 )



.dcOP
.dc temp lin '21' '-40' '150' name=dc

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe dc v(vref)

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL






.end

# References
[1]  H. Banba, H. Shiga, S. Umezawa, T. Miyaba, T.Tanzawa, S. Atsumi, K.Sakui, “A CMOS Bandgap Reference Circuit with Sub-1-V Operation,” IEEE  
     J.SolidStateCircuits, vol. 34, pp. 670–674, May 1999.
[2]  A. K. Singh, P. K. Pal, and M. Pattanaik, “A wide temperature range voltage bandgap reference generator in 32nm CMOS technology”, in IEEE Global Conference 
     on Communication Technologies (GCCT), pp. 696-699, 2015. 
[3]  Adimulam, M. K., and K. K. Movva. ”A lowpower CMOS current mode bandgap reference circuit with low temperature coefficient of output voltage,” In 
     Microelectronics and Electronics (PrimeAsia), 2012 Asia Pacific Conference on Postgraduate Research in, pp. 144-149. 2012.

# Acknowledgements

-[Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)

-[Cloud Based Analog IC Design Hackathon](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/')

-[Synopsys India](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/')

-[Chinmay panda, IIT Hyderabad](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/')

# Author
Kashish Goyal
