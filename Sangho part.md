# 2. Theoretical background
## Section 1. Coordinates
$\quad$ Understanding the Earth Centered Inertial Coordinates (ECI), Body Fixed Coordinates (BFC), and Wind Coordinates (WC) is crucial for deriving equations that describe the aerodynamics of aircraft flight. Precise comprehension of these coordinate systems enables the mathematical modeling of the physical forces acting upon an aircraft, facilitating an accurate prediction of its motion within each respective coordinate framework. The following provides an explanation of each coordinate system utilized in describing aircraft flight dynamics.

### 1. Wind Coordinates  
$\quad$ The wind coordinate system is utilized to represent aerodynamic forces significantly impacting an aircraft's motion. Its starting point is aerodynamic center (which is expressing aerodynamic force of aircraft), with the 𝑋-axis oriented along the direction of the wind. Following the right-hand rule, the 𝑌-axis is perpendicular to the 𝑋-axis, pointing towards the right wing, while the 𝑍-axis is defined as perpendicular to the 𝑋𝑌 plane, pointing downwards from the aircraft. With respect to the aircraft's body-fixed coordinate system, the rotation around the 𝑌-axis with respect to the wind direction is the Angle of Attack, and the rotation around the 𝑍-axis is the Side Slip Angle. The following equations represent the Angle of Attack and Side Slip Angle, accompanied by a diagram illustrating the wind coordinate system.
<center>

$\alpha = atan(\frac{w}{u}), \beta = acos(\frac{u}{v})$

!["Wind Coor"](/final%20image/image%204.jpeg)

< Picture 4 > Wind Coordinates

</center>

<br>
<p align="center"> 8  

---------------------------------------------------------------------------------

### 2. Body Fixed Coordinates

$\quad$ The body-fixed coordinate system is employed to represent the forces and moments influencing an aircraft's motion. Its origin is the aircraft's center of gravity, with the 𝑋-axis pointing in the direction of the aircraft's nose. Following the right-hand coordinate system, the 𝑌-axis is perpendicular to the 𝑋-axis, pointing towards the right wing of the aircraft, while the 𝑍-axis is oriented vertically, pointing downwards from the aircraft in the 𝑋𝑌 plane. The following diagram illustrates the body-fixed coordinate system.

<center>

!["Body Coor"](/final%20image/image%205.jpeg)

< Picture 5 > Body Fixed Coordinates

</center>

<br>
<p align="center"> 9

---------------------------------------------------------------------------------

### 3. Earth Centered Inertial Coordinates

$\quad$ The Earth Centered Inertial Coordinate System (ECI) is a coordinate system used to represent the motion of an aircraft in relation to the Earth. The origin is at the center of the Earth, with the 𝑋-axis pointing towards the vernal equinox from the Earth's center, and the 𝑍-axis aligned with the Earth's rotational axis. The 𝑌-axis is defined as perpendicular to the 𝑋𝑍 plane, following the right-hand coordinate system. The following diagram illustrates the Earth Centered Inertial Coordinate System.

<center>

!["ECI"](/final%20image/image%206.jpeg)

< Picture 6 > ECI Coordinates

</center>

<br>
<p align="center"> 10

---------------------------------------------------------------------------------

## Section 2. 6-DOF Equation for Flight

$\quad$ "6-DOF Equation for Flight (or Flight dynamics equations)" represent the aircraft's motion based on the forces and moments acting on the aircraft. The velocity and angular velocity of the aircraft change due to the forces and moments, representing the aircraft's state in both body-fixed coordinate system and Earth-centered inertial coordinate system. The following are fundamental equations utilized in flight dynamics equations.

### 1. CLMEs

$\quad$ Conversation of the linear Momentum Equations(CLMEs) is an equation derived from Newton's second law, allowing us to determine the rate of change of linear velocity for the current state of the aircraft based on the forces acting on the aircraft in the body-fixed coordinate system.

<center>

!["CLMEs"](/final%20image/6-DOF/CLMEs.jpeg)

 CLMEs

</center>

### 2. CAMEs
$\quad$ Conversation of the Angular Momentum Equations(CAMEs) is an equation derived from Newton's second law, allowing us to determine the rate of change of angular velocity for the current state of the aircraft based on the moments acting on the aircraft in the body-fixed coordinate system. 

<center>

!["CAMEs"](/final%20image/6-DOF/CAMEs.jpeg)

 CAMEs

</center>

<br>
<p align="center"> 11

---------------------------------------------------------------------------------

### 3. FPEs

$\quad$ "Flight path equation(FPEs)" is an equation that transforms the body-fixed coordinate system's linear velocity into the Earth-centered inertial coordinate system's linear velocity through a rotation matrix.

<center>

!["FPEs"](/final%20image/6-DOF/FPEs.jpeg)

 FPEs

</center>

### 4. KEs

$\quad$ "Kinematic equation(KEs)" is an equation that transforms the body-fixed coordinate system's angular velocity into the Earth-centered inertial coordinate system's angular velocity through a rotation matrix.

<center>

!["KEs"](/final%20image/6-DOF/KEs.jpeg)

 KEs

</center>

### 5. GEs

$\quad$ "Gravity equation" is an equation that transforms the gravitational component acting along the 𝑍-axis in the Earth-centered inertial coordinate system into the body-fixed coordinate system.

<center>

!["GEs"](/final%20image/6-DOF/GEs.jpeg)

 GEs

</center>

<br>
<p align="center"> 12

---------------------------------------------------------------------------------

## Section 3. Bezier Curve

$\quad$ "A Bézier Curve" is a mathematical curve defined using polynomial functions. Generally, an $𝑛$-th degree Bézier curve is defined by $𝑛+1$ control points. Widely employed in graphic design and computer graphics, Bézier curves are primarily used to create smooth and intricate curves by manipulating control points. Also, They find applications in various fields such as animation, user interface design, and robotics to control smooth movements. The mathematical expression below represents an 𝑛-th degree Bézier curve.

<center>

!["Bezier Curve"](/final%20image/Equations/Bezier.jpeg)

$𝑛$-th degree Bézier Curve

</center>

$\quad$ _B_(𝑡) represents the position of an 𝑛-th degree Bézier curve for the parameter 𝑡, where 𝑃𝑖 denotes control points. The shape of the Bézier curve is controlled by the positions of these control points. 𝐵𝑖,𝑛(𝑡) adjusts the weights of each control point as the 𝑛-th degree Bézier basis function, influencing the shape of the curve. The parameter 𝑡 takes values from 0 to 1, and as it varies, the Bézier curve smoothly moves and transforms.

<br>
<p align="center"> 13

---------------------------------------------------------------------------------

## Section 4. Target Aircraft

$\quad$ The research target aircraft is the Urban Air Mobility (UAM) demonstrator, KP-2C, designed and manufactured by Konkuk Aerospace Design &middot; Airworthiness Institute in collaboration with the Carbon Tech Institute. The KP-2C features a box-wing configuration, with a total of four propellers, two ailerons, and two V-shaped tail wings. During vertical takeoff, it generates thrust in the vertical direction using all four propellers, enabling it to rotate like a conventional helicopter. In cruise mode, it transitions by horizontally tilting the front two propellers while keeping the rear two propellers inactive, resembling the flight of a fixed-wing aircraft. During transition flight, all four propellers and control surfaces are utilized to control attitude and speed, with adjustments to the tilt angle of the front propellers. Below are the specifications and configuration of the KP-2C.

<center>

!["KP-2C"](/final%20image/image%207.jpeg)

< Picture 7 > KP-2C (Left: Model, Right: Physical Aircraft)

<br>
<p align="center"> 14

---------------------------------------------------------------------------------


!["Specifications of KP-2C"](/final%20image/Chart/Chart%201.jpeg)

< Chart 1 > Specifications of KP-2C

</center>

<br>
<p align="center"> 15

---------------------------------------------------------------------------------

# 3. Transition Flight Schedule

## Section 1. Transition Flight Scheduling

$\quad$ Transition flight scheduling begins with speed scheduling and is derived through lift distribution load factor scheduling and trim analysis. The figure below illustrates the entire transition flight scheduling process.

<center>

!["Trans Process"](/final%20image/image%208.jpeg)

< Picture 8 > Transition Flight Scheduling Process

</center>

<br>
<p align="center"> 16

---------------------------------------------------------------------------------
### 1. Speed Schedule
$\quad$ In the transition flight process, the aircraft must accelerate from a stationary state to the target speed. The rate of speed change in this process influence the rate of acceleration, and the magnitude of such changes affects the aircraft's flight performance or required performance. If the speed change during the transition flight process is too rapid, it demands a significant acceleration, while if it is too slow, reaching the target speed within the given time may be unattainable. Additionally, if the speed change is not smooth at the beginning and end of the transition flight, abrupt acceleration or deceleration may occur, and stable settling to the target speed becomes challenging because acceleration persists after the end moment. Therefore, speed scheduling should be designed to ensure that the acceleration is zero at the start and end points and that the acceleration is not excessively high in between.

### 2. Lift distribution load factor (Load factor)
$\quad$ Lift distribution load factor refers to the ratio of forces in the vertical (𝑍-axis) direction between the lift generated by the wings and the thrust generated by the propellers in the body-fixed coordinate system. Typically, VTOL (Vertical Take-Off and Landing) aircraft have a higher thrust-dominant load factor at low speeds, while at high speeds, the lift from the wings dominates. These variations have a significant impact during transition flight segments where the flight speed undergoes significant changes. Therefore, inducing a smooth change in the lift distribution load factor is crucial for ensuring stability.

$\quad$ During transition flight segments, the load factor can vary significantly depending on the aircraft's attitude. To avoid affecting flight stability, it is necessary to maintain the attitude from the pre-stalling angle and target a load factor of 1 (where lift equals weight) at the target speed.

<br>
<p align="center"> 17

---------------------------------------------------------------------------------

$\quad$ For the target eVTOL Tiltrotor aircraft, it is essential to set the attitude between the stalling angle and the level state at 0 degrees in such a way that the lift distribution load factor becomes 1 at the target speed. By maintaining a high Angle of Attack, lift can equal weight at relatively low speeds, while keeping a Low Angle of Attack can achieve the same at higher speeds. The lift distribution load factor diagram is determined differently based on the aircraft's performance. The following is a general lift distribution load factor diagram.

<center>

!["load factor"](/final%20image/image%209.jpeg)

< Picture 9 > Lift distribution load factor

</center>

$\quad$ The lift distribution load factor for the wing as a function of flight speed satisfies the equation below. Through numerical analysis techniques using lift distribution load factor, one can derive the flight angle of attack at the corresponding speed. By utilizing the previously planned speed schedule and the designed lift distribution load factor for the wing, it is possible to obtain the flight pitch angle schedule and the rate of change of flight pitch angle schedule.

<center>

!["Eqation"](/final%20image/Equations/Lift%20Ratio.jpeg)

< Load Factor Equation >

</center>

<br>
<p align="center"> 18

---------------------------------------------------------------------------------

### 3. Aircraft Modeling

$\quad$ The physical forces acting on the aircraft include lift, thrust, and gravity. Lift is the force generated by the wings, acting at the center of lift, which is the origin in the wind coordinate system. Thrust is generated by each propeller and acts at the center of each propeller. Gravity acts at the center of gravity. In the case of transition flight, the tilt angle of the propellers changes, significantly affecting the longitudinal dynamics. Therefore, in this paper, only the longitudinal factors that have a significant impact on transition flight are considered to reduce complexity.

$\quad$ In the case of lift modeling, element-based modeling was employed to model the wing and tail control surfaces, which influence the lift coefficients. Using the situation where the angle of the tail control surface is 0 degrees as a reference, the lift coefficient static term, which changes with the wing's flight pitch angle, was modeled. Using this as a reference, the lift coefficient control term, which changes with the angle of the tail control surface at the corresponding flight pitch angle, was modeled. Additionally, coefficient variations caused by changes in angular velocity were ignored since the aircraft's attitude changes were not significant. The following are the modeled equations for lift, drag, and pitching moment.

<center>

![Coeffiecent](/final%20image/Equations/C.jpeg)

< Modeled Equation >

</center>

$\quad$ The forces and moments generated by the lift coefficients mentioned above can be expressed taking into account atmospheric density and flight speed as follows:

<center>

![Force&Moment](/final%20image/Equations/Force%20and%20Moment.jpeg)

< Forces and Moments >

</center>

<br>
<p align="center"> 19

---------------------------------------------------------------------------------

$\quad$ For the thrust, modeling was based on wind tunnel tests of the aircraft's propellers to consider the maximum performance while accounting for performance limits. During the trim analysis process, the thrust is derived as the required thrust, requiring only information on the maximum performance to consider physical constraints. The wind tunnel tests were conducted in the Konkuk University low-speed wind tunnel, using the actual unmanned aircraft's electric propulsion system. The tests varied the propeller inflow velocity to consider the performance changes with varying propeller inflow velocities. Below are photos of the wind tunnel test equipment and the results.

<center>

!["Wind Tunnel"](/final%20image/image%2010.jpeg)

< Picture 10 > Konkuk University low-speed wind tunnel

!["Thrust Tester"](/final%20image/image%2011.jpeg)

< Picture 11 > Thrust Tester

</center>

<br>
<p align="center"> 20

---------------------------------------------------------------------------------

$\quad$ The thrust performance data corresponding to changes in propeller inflow velocity is shown in the following pictures. The tests were conducted by varying the propeller inflow velocity in 5 $m/s$ intervals from 0 $m/s$ to 20 $m/s$.

<center>

!["Performance Data"](/final%20image/image%2012.jpeg)

< Picture 12 > Propeller Thrust test data

</center>

$\quad$ According to the wind tunnel test results, it is observed that the rotational speed and thrust increase with throttle input. Additionally, concerning the variation in propeller inflow velocity, it is noted that the maximum thrust decreases as the propeller inflow velocity increases. To account for the decrease in maximum thrust, a third-degree polynomial interpolation was performed to predict the performance changes within the unmeasured range. Below is the result picture using the third-degree polynomial interpolation.

<br>
<p align="center"> 21

---------------------------------------------------------------------------------

<center>

!["Thrust performance"](/final%20image/image%2013.jpeg)

< Picture 13 > Maximum thrust performance as a function of propeller inflow velocity

</center>

$\quad$ In the case of gravity, it acts in the direction from the aircraft's center of gravity towards the Earth's center. The model equations and diagrams summarizing the forces and moments considered above, in the longitudinal direction, in the Earth-centered coordinate system are as follows:

<center>

!["modeling Equation"](/final%20image/Equations/Modeling.jpeg)

< Model Equation >

!["KP-2C Modeling"](/final%20image/image%2014.jpeg)

< Picture 14 > KP-2C Modeling

</center>

<br>
<p align="center"> 22

----------------------------------------------------------------------------

### 4. Trim analysis
$\quad$ To derive the transition flight schedule, trim analysis was performed to obtain control inputs that satisfy the trim conditions over time, including pitch attitude, angular velocities, flight speed, and acceleration. The purpose of trim analysis is to determine control values that satisfy the given flight state, confirming the feasibility of flight under the interpreted conditions. For this, an aircraft model is necessary, including propulsion, lift, and other physical force models.

$\quad$ According to the trim analysis conditions, the forces and moments in the Earth-centered coordinate system must satisfy the given flight state. In this context, the force in the X-axis direction of the Earth-centered coordinate system in the modeled aircraft must be equal to the product of X-axis acceleration and mass at the corresponding flight speed. Similarly, the force in the Z-axis direction must be equal to the product of Z-axis acceleration and mass at the given flight speed. The Y-axis moment should be equal to the product of inertia moment and angular velocity. The following represents the trim analysis equations.

<center>

!["Trim Analysis Equation"](/final%20image/Equations/Trim.jpeg)

< Trim Analysis Equation >

</center>

<br>
<p align="center"> 23

----------------------------------------------------------------------------

$\quad$ In trim analysis, the given control elements are the thrust from the front propeller, thrust from the rear propeller, tail control surface angle, and propeller tilt angle. There are a total of four variables to be solved for three equations, resulting in an over-constrained system. To address this, one of the variables, the propeller tilt angle, was assigned a value, and the analysis was performed by solving the three remaining equations with three variables.Unlike conventional aircraft where the thrust components are not distinguished between front and rear, the Tiltrotor's specific configuration introduces additional variables. 

$\quad$ Trim analysis is carried out under given conditions of flight speed, acceleration, angular velocity, and propeller tilt angle, determining the required thrust to satisfy the trim conditions by analyzing the force in the Z-axis direction and the moment in the Y-axis direction in the Earth-centered inertial coordinate system. The following matrix equation represents the balance of forces and moments in the Z and Y directions in the Earth-centered inertial coordinate system to obtain the required thrust.

<center>

!["Thrust matrix equation 1"](/final%20image/Equations/Thrust%201.jpeg)

!["Thrust matrix equation 2"](/final%20image/Equations/Thrust%202.jpeg)

< Thrust matrix equation >

</center>

<br>
<p align="center"> 24

----------------------------------------------------------------------------

$\quad$ Subsequently, employing numerical methods, the trim condition-satisfying tail control surface angle is determined from the force equation in the X-axis direction. This process is iteratively conducted to obtain the required thrust and control surface angles satisfying the trim conditions for all three axes. By performing these iterations for various propeller tilt angles, the range of propeller tilt angles that satisfy the trim conditions is identified. The magnitude of the required thrust varies with the propeller tilt angle. In this paper, a propeller tilt schedule is determined by selecting the required thrust as the objective function and finding the propeller tilt angle that minimizes the required thrust. The following diagram illustrates the Tiltrotor trim analysis process.

<center>

!["Tiltrotor trim analysis process"](/final%20image/image%2015.jpeg)

< Picture 15 > Tiltrotor trim analysis process

</center>

<br>
<p align="center"> 25

----------------------------------------------------------------------------
## Section 2. Transition Flight Schedule for the Target Aircraft
