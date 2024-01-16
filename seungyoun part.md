# 4. Establishing an eVTOL Tiltrotor Flight Simulation Environment

## Section 1. Electric Propulsion Model (KFDS)
$\quad$ The target aircraft is an eVTOL Tiltrotor aircraft that uses an electric propulsion system. Through flight simulation, an electric propulsion model was added to JSBSim, an open source based flight dynamics software, to predict the flight state of the aircraft. The electric propulsion system of the target aircraft consists of a battery, a power distribution board (PDB), an electronic speed controller (ESC), a blushless direct current (BLDC) motor, and a propeller. The power distribution board does not require any special modeling because it serves to distribute the power required by each component. Therefore, the 
remaining components except the power distribution board were modeled. The figure below is the architecture of the electric propulsion model.

<center>

  ![< Picture 24 > KFDS Architecture](final%20image/image24.png)
  
  < Picture 24 > KFDS Architecture

</center>

<br>
<p align="center">35

--------------------------------------------------------------------------
### 1. Battery Model
$\quad$ Batteries store electrical energy and provide electricity to the aircraft during flight. The type and capacity of the battery greatly affects the flight time and performance of the aircraft, and the target aircraft uses a lithium polymer (Li-Po) battery. Lithium polymer batteries are lightweight and have high energy density. They are widely used in various electronic devices and mobile devices, and are also widely used in unmanned aerial vehicles. These lithium polymer batteries can store high energy per unit weight at high energy density and can store energy for a long period of time at a low discharge rate. In addition, since it can handle high discharge current, it can cope with sudden power changes during flight, maintain high voltage, and have relatively light weight. The lithium polymer battery model tables the voltage performance that varies depending on the amount of charge, and models the capacity used to drive other components. The equation below is a voltage model provided by the battery as ESC.

<center>

$U_{Battery_{out}} = U_{Battery} - I_{Battery} \cdot R_{Battery}$

</center>



