#  1. Introduction 

## Section 1. Research Background
$\quad$ In this study, we explain the necessity of transition flight scheduling for eVTOL tiltrotor aircraft.

### 1. (UAM - Urban Air Mobility)

$\quad$ As civilization progresses worldwide and populations increase, there's a deepening concentration of people in major cities, evolving them into mega-cities. These urban areas face significant economic losses due to congestion in surface transportation, surpassing the two-dimensional limits of conventional urban transport. This has led to serious environmental issues, prompting the necessity for innovative transportation solutions.

$\quad$ The urban air mobility (UAM) is proposed as a solution to extend urban transportation from 2D to 3D, and it has garnered significant research and investment from industries and research institutions to address numerous challenges in enabling flights within densely populated city areas.

$\quad$ For safe flights in urban areas, ensuring flight stability is crucial while also employing propulsion systems that generate minimal noise to reduce urban noise levels. Additionally, using environmentally friendly energy sources to prevent environmental issues is essential. To operate in urban areas without runways, it needs to be capable of vertical takeoff and landing (VTOL). To address these challenges, electric Vertical Takeoff and Landing (eVTOL) aircraft have emerged.

<p align="center"> 1

------------------------------------------------------------------------

### 2. eVTOL (electric Vertical Takeoff & Landing) Tiltrotor

$\quad$ eVTOL stands for electric Vertical Takeoff and Landing aircraft, which are capable of vertical takeoff and landing using electric propulsion systems. These aircraft generate thrust in the vertical direction, enabling them to perform vertical takeoffs and landings. eVTOLs that can perform vertical takeoffs do not require a separate runway, making them suitable for urban air mobility or unmanned drone systems.

$\quad$ eVTOL aircraft are designed to be powered by electricity, offering lower carbon emissions compared to conventional aircraft using fossil fuels, as well as reduced noise pollution and potentially lower operational costs. These eVTOLs come in three main configurations: Multirotor, Lift & Cruise, and Tiltrotor.

$\quad$ Among these, the Tiltrotor configuration can vertically take off by orienting the propellers in the vertical direction of the aircraft, allowing it to fly like a helicopter. During cruise, the propellers can be oriented horizontally, enabling the aircraft to fly like a fixed-wing airplane. The Tiltrotor configuration combines the advantages of both helicopter and fixed-wing aircraft, making it a subject of active research in various research institutions and industries recently.

$\quad$ Tiltrotor aircraft have a unique flight phase called transition flight, where the direction of the propellers is changed to alter the flight mode. During transition flight in a tiltrotor aircraft, the thrust direction of the propellers changes, leading to a transformation in the aircraft's configuration and a complex variation in its flight characteristics. Consequently, the transition flight phase of a tiltrotor aircraft is considered highly unstable, posing challenges that necessitate research to ensure flight safety and guarantee the secure operation of tiltrotor aircraft.

<p align="center"> 2

-----------------------------------------------------------------------

## Section 2. Analysis of Existing Similar Studies

$\quad$ Numerous studies are underway to ensure the flight stability during transition phases, which are inherently unstable, for the operation of safe eVTOL tiltrotor aircraft. In this section, we analyze existing similar research on securing the transitional flight stability of eVTOL tiltrotor aircraft and present the limitations of these studies, clearly establishing the need for our research.

### 1. Interpretative Study in Performance of Transition Flight Area

$\quad$ In a paper authored at NASA Ames Research Center, an analysis was conducted to understand the flight complexity of tiltrotor aircraft by examining the airspeed and flight path angle or vertical velocity at various flight regimes based on propeller tilt angles. To achieve this, longitudinal flight dynamics modeling of Bell's XV-15 was employed. Trim analysis was conducted based on flight speed and propeller tilt angles to analyze the regions where stable flight was feasible.

<center>
 
 ![< image >](final%20image/image1.png)

</center>


 <p align="center"> 
 < Picture 1 > Transition Corridor for Various Rotor Tilt Angels


 <p align="center"> 3

--------------------------------------------------------------------------

 ### 2. Research on Transition Flight Control


 $\quad$ In a paper from the University of Cranfield in the UK, the longitudinal flight control system of an eVTOL tiltrotor aircraft was developed. In this process, instead of manipulating the propeller tilt angle, the pilot adjusted the flight speed using minimal power curves and numerical optimization to determine the optimal tilt schedule. To achieve this, trim analysis of the aircraft's performance was conducted, utilizing this information to assess the feasible flight envelope based on propeller tilt angles and determining the optimal tilt schedule.

$\quad$ Afterward, following the optimal slope schedule, specifying trim points for linearization, and gain scheduling along the linearized points of the PID controller, we designed the controller. Through this controller, when adjusting the desired speed, the controller gain values and propeller tilt angles automatically change, enabling flight

<center>

 ![< image >](final%20image/image2.png)

</center>

<p align="center">
< Picture 2 > Optimal Propeller Tilt Schedule

<p align="center"> 4


------------------------------------------------------------------------------------

### 3. Limitations of Existing Similar Research
$\quad$ Through the analysis of previous similar studies, the limitations of the research were identified, and the necessity of this study is presented. The study focuses on confirming the flight characteristics of eVTOL tiltrotor aircraft for stable transition flight by interpreting the aircraft's trim, selecting linearization points, and designing a flight control system based on gain scheduling.

$\quad$ This research enabled eVTOL tiltrotor aircraft to control altitude and speed during transition flight, depending on the flight speed. However, it had limitations in controlling the magnitude of acceleration or adjusting it for transition flight duration. Additionally, through studies aiming to complete transition flights within a given time frame, it was possible to allocate appropriate time for mission-specific transition flights with higher operational risk due to lower flight stability and operate accordingly. Such research could offer a more diverse range of control methods for flight control.

$\quad$ Therefore, in this study, overcoming the limitations of previous research and based on the necessity of the research, we aim to conduct flight dynamics modeling of the target aircraft, and through trim analysis, generate propeller tilt schedules and flight state schedules considering transition flight time and acceleration. By doing so, we intend to provide the flight control system with the set values for transition flight schedules, ensuring that the aircraft can complete transition flight stably according to the transition flight schedule, thereby enabling the aircraft to achieve stable transition flight dynamically.

<p align="center"> 5

-------------------------------------------------------------------------------------
## Section 3. Research Objectives

$\quad$ This research aims to generate a transition flight schedule for stable transition flights of eVTOL Tiltrotor aircraft. Urban Air Mobility (UAM) aircraft operating in urban areas with high population density must ensure flight safety to prevent accidents. Additionally, creating a reliable transition flight schedule considering the time and acceleration required for transition flights is necessary.

$\quad$ To generate a transition flight schedule considering time and acceleration, it's necessary to perform aerodynamic modeling of the aircraft under study and predict its physical performance through trim analysis. Additionally, considering the aircraft's motion, a transition flight schedule involving the aircraft's movement over time needs to be created.

$\quad$ Therefore, the purpose of this study is to generate a transition flight schedule for the stable transition flight of eVTOL Tiltrotor aircraft. Through this, enabling the safe operation of Tiltrotor aircraft, which offers numerous advantages among eVTOL aircraft configurations, through time-conscious stable transition flights in urban areas. The following is the overall research process architecture.

<p align="center"> 6

-----------------------------------------------------------------------------------
 <center>
 
 ![< image >](final%20image/image3.png)

</center>

<p align="center">  < Picture 3 > Overall research process architecture

<p align="center"> 7  

---------------------------------------------------------------------------------

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

![coefficient](/final%20image/Equations/C.jpeg)

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
$\quad$ Based on the previous information, the transition flight schedule for the target aircraft was derived. The transition flight schedule was developed for two designed lift distribution schedules. The target time and target speed for the transition flight schedule were set. The target time utilized the default setting time of 7 seconds for the transition flight algorithm in the flight control software, for future comparison and analysis. The target speed was set to allow a 20% margin from the stall speed. The stall speed is the speed at which the lift generated equals the weight of the aircraft, occurring at the maximum lift coefficient. The following are the formulas for calculating the stall speed, target speed, and the aircraft's lift coefficient graph.

<center>

!["Lift coefficient"](/final%20image/image%2016.jpeg)

< Picture 16 > Lift coefficient graph

!["Speed Equation"](/final%20image/Equations/Required%20Speed.jpeg)

< Required Speed Equation >

</center>

<br>
<p align="center"> 26

----------------------------------------------------------------------------
### 1. The speed schedule for the target aircraft
$\quad$ The speed schedule for the target aircraft is designed for two cases, denoted as 𝐴 and 𝐵. The speed schedule utilizes a 3rd-degree Bezier curve to ensure that the acceleration is zero at start and end points. In the first case 𝐴, the design involves smoothly accelerating and decelerating, using a 3rd-degree Bezier curve with four control points. The starting and ending points are fixed, and the two middle control points are adjusted. These two control points are positioned at 20% and 80% of the total time duration. Below are the control points and the resulting speed schedule obtained from the 3rd-degree Bezier curve. 

<center>

!["Bezier chart"](/final%20image/Chart/chart%202.jpeg)

< chart 2 > The control point information for the speed schedule 𝐴 Bezier curve

!["Speed Schedule A"](/final%20image/image%2017.jpeg)

< Picture 17 > Speed Schedule A

</center>

<br>
<p align="center"> 27

----------------------------------------------------------------------------
$\quad$ The second case, 𝐵, is designed to accelerate slowly and then decelerate rapidly near the end. For the 3rd-degree Bezier curve, the starting and ending points are fixed, and the two middle control points are adjusted. These middle control points are positioned at 60% and 80% of the total time duration. The following are the control point details for the 3rd-degree Bezier curve and the resulting speed schedule. Additionally, comparison graphs depicting the variation in jerk, acceleration, speed, and distance for both speed schedules are provided.

<center>

!["Bezier chart B"](/final%20image/Chart/chart%203.jpeg)

< chart 3 > The control point information for the speed schedule _B_ Bezier curve

!["Speed Schedule B"](/final%20image/image%2018.jpeg)

< Picture 18> Speed Schedule B

!["Comparison"](/final%20image/image%2019.jpeg)

< Picture 19 > Comparsion of Speed Schedule A and B

</center>

<br>
<p align="center"> 28

----------------------------------------------------------------------------
### 2. Lift Distribution of the Target Aircraft
$\quad$ Based on the designed aircraft speed schedule, the aircraft's angle of attack schedule was derived through the lift distribution chart. Here, as the lift distribution changes, the angle of attack schedule of the aircraft also changes. To analyze the influence of the lift distribution chart, two different lift distribution charts were designed.

$\quad$ The first lift distribution chart maintains a constant angle of attack during the transition flight process to ensure that the wing's lift distribution reaches 1 at the target speed. The second lift distribution chart also reaches 1 at the target speed, but for a smoother change in lift distribution, the slope of the wing's lift distribution with respect to speed is designed to be 0 at the target speed using a Bezier curve.

$\quad$ The first lift distribution chart is expressed as a constant angle of attack, denoted as 'Constant', and the second lift distribution chart varies the angle of attack, denoted as 'Change'. The following are the designed lift distribution charts and the resulting schedules for angle of attack and angle of attack rate over time.

<br>
<p align="center"> 29

----------------------------------------------------------------------------

<center>

!["Bezier chart for Lift distribution"](/final%20image/Chart/chart%204.jpeg)

< chart 4 > The control point information for Lift distribution Bezier curve

!["Graph of Lift distribution"](/final%20image/image%2020.jpeg)

< Picture 20 > Graph of Lift distribution

</center>

<br>
<p align="center"> 30

----------------------------------------------------------------------------

<center>

!["AoA schedule"](/final%20image/image%2021.jpeg)

< Picture 21 > AoA schedule above Graph of Lift distribution

!["AoA rate schedule"](/final%20image/image%2022.jpeg)

< Picture 22 > rate of AoA schedule above Graph of Lift distribution

</center>

<br>
<p align="center"> 31

----------------------------------------------------------------------------
### 3. Trim analysis of the Target aircraft
$\quad$ Utilizing the previously derived aircraft motion schedule, a trim analysis was conducted. In the trim analysis process, the propeller tilt angle that minimizes the total required thrust of the aircraft was determined, with the goal of maintaining a constant altitude. For this reason, the trim analysis focused on the longitudinal direction, and the aircraft motion schedule considered the elements in the 𝑋-axis direction in the Earth-centered inertial coordinate system. Additionally, it was assumed that the pitch attitude angle and angle of attack during flight were the same. The following are the results obtained through the trim analysis method described earlier.

<br>
<p align="center"> 32

----------------------------------------------------------------------------

<center>

!["Tirm Analysis"](/final%20image/image%2023.jpeg)

< Picture 23 > The transitional flight schedule of the target aircraft

</center>

<br>
<p align="center"> 33

----------------------------------------------------------------------------
$\quad$ According to the transitional flight schedule derived from the trim analysis, it is commonly observed that as the flight speed of the target aircraft increases, the front thrust gradually increases while the rear thrust decreases, reaching zero at a specific time. Additionally, with the change in pitch attitude, there is a slight variation, but consistently, an initially negative pitching moment is generated, followed by a positive pitching moment produced using the tail control surface.

$\quad$ Regarding the flight angle of attack, a larger angle of attack results in an increased difference in the magnitude of front and rear thrust. When an increased flight angle of attack is required, it is noted that a smaller front propeller tilt angle leads to a larger front thrust compared to the rear thrust.

$\quad$ These results can be interpreted based on the aircraft's configuration and flight characteristics. The target aircraft has the thrust center of the propeller positioned above the aircraft's center of gravity. Therefore, as the front propeller tilt angle decreases, the influence of the pitching moment generated by the front thrust diminishes, resulting in a transition from positive to negative pitching moment. This change in the direction of the thrust-induced pitching moment highlights the active use of the tail control surface for pitch control. Similarly, the reduction in the need for rear propeller thrust is observed as the tail control surface generates a positive pitching moment that counteracts the negative pitching moment produced by the front propeller thrust.

<br>
<p align="center"> 34

----------------------------------------------------------------------------

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

### 2. ESC Model
$\quad$ The ESC electronically controls the speed of the BLDC motor and transmits the power of the motor. It controls the thrust and torque generated by precisely controlling the rotational speed of the motor and supports the efficient operation of the motor. In addition to controlling the rotational speed of the motor through ESC, it also functions to protect the motor from overheating, overcurrent, short circuit, etc., monitors the voltage of the battery, and protects the battery from discharging. The ESC operates through the reception of the PWM signal, controls the voltage applied to the motor in the internal circuit in accordance with the PWM signal, and controls the rotation of the motor. ESC, used together with BLDC motors, is widely used in unmanned aerial vehicles. The equation below is a voltage model provided by ESC to BLDC motor.

<center>

$U_{ESC} = \delta_{throttle} \cdot R_{Battery} - I_{ESC} \cdot R_{ESC}$

</center>

<br>
<p align="center">36

--------------------------------------------------------------------------
### 3. BLDC Motor Model
$\quad$ The BLDC motor generates rotational motion and rotates the propeller to generate thrust and torque. Since there is no brush, it has the characteristic of operating efficiently without friction and energy loss of the brush, and each motor provides performance in specific flight conditions. It provides excellent performance in high speed and high power applications, and can achieve a higher number of rotations than a brush motor. In addition, there is no external physical contact due to rotation using a magnetic force, and accurate control is possible through an electronic control device. This feature is used in various fields such as unmanned aerial vehicles, electric bicycles, robots, and industrial automation. The equation below is the torque generated by the BLDC motor, the power provided by the propeller, and the current model required by the ESC.

<center>

$Q_{Motor}$ = $K_{t} \cdot (I_{Motor_{required}} - I_{Motor_{idle}}$)

$P_{Motor}$ = $Q_{Motor} \cdot \Omega_{propeller}$

$I_{Motor_{required}} = \frac {U_{ESC} - RPM/ K_{v}} {R_{Motor}}$

</center>

<br>
<p align="center">37

--------------------------------------------------------------------------
### 4. Propeller Model
$\quad$ The propeller generates the thrust and torque of the aircraft through the aerodynamic force in the propeller by the rotational motion generated by the BLDC motor. The performance varies depending on the length, the shape of the propeller cross-section airfoil, the twist, and the pitch angle. The moment of inertia, diameter, the number of blades, and the geometric pitch angle of the propeller were considered, and in order to consider the performance of the propeller that changes according to the forward speed of the aircraft, it was modeled as the thrust and power coefficient according to the forward ratio. The equation below is a model for thrust, power, forward ratio, propeller efficiency, and rotation speed.

<center>

$T$ = $C_{thrust} \rho n^2 D_{prop}^4$

$P$ = $C_{power} \rho n^3 D_{prop}^5$

$J$ = $\frac {V_{inflow}}{nD}$

$\eta$ = $\frac {C_{thrust}V_{inflow}}{C_{power}nD}$

$RPM=RPS + \frac {60(P_{Motor}-P_{required})}{2I_{{xx}_{prop}} \cdot \Omega_{propeller}} \cdot \pi$

</center>

<br>
<p align="center">38

--------------------------------------------------------------------------
## Section 2. Model Database
$\quad$ A database used in aircraft models is needed to predict the condition of the aircraft. The database can express the forces and moments acting on the aircraft. The model database of aircraft is largely divided into shape, weight and balance, aerodynamic, and propulsion.

### 1. Shape Database
$\quad$ The aircraft shape database contains shape information such as the main blade area, length, cord length, and the origin of the wind coordinate system. The origin of the wind coordinate system is defined as AeroRP, and if the aerodynamic force is the position acting on the model and does not exactly match the center of gravity, an additional moment or torsional force is generated. Other aircraft models are not affected, but there are tail control planes and position information due to various needs. The tail control plane information is used by the JSBSim Turbulence code and does not affect the actual flight dynamics model. EYEPOINT is the point at which the pilot's point-in-time position is calculated, and the gravitational acceleration felt by the pilot during flight is calculated. VRP is the origin of the world position in an aircraft. The following is the aircraft shape database information.
</center>

<br>
<p align="center">39

--------------------------------------------------------------------------
<center>

  ![< Graph 5 > Shape Database](final%20image/graph5.png)
  
  < Chart 5 > Shape Database

</center>

<br>
<p align="center">40

--------------------------------------------------------------------------
### 2. Weight and Inertia Database
$\quad$ The weight and inertia database contains information on the physical properties caused by aircraft mass. The moment of inertia creates a slower rotational force than the low value where the high value is not, and the $I_{XZ}$, $I_{YZ}$, and $I_{XY}$ terms are generally zero because the $X$, $Y$, and $Z$ axes are the main axes. However, in the case of an asymmetric aircraft shape, a term may exist because the $X$, $Y$, and $Z$ axes do not match the symmetrical axis of the aircraft. In the case of weight, it represents the empty weight of the aircraft, but in this paper, the weight of each element is considered as 0, and the total weight is represented by generating weight and inertia data for the whole during the analysis process. Therefore, the weight and inertia database shows information for the entire aircraft. The center of gravity represents the origin of the fuselage fixed coordinate system and is the point of action of gravity. The following is information on the weight and inertia database.

<center>

  ![< Graph 6 > Weight and Inertia Database](final%20image/graph6.png)
  
  < Chart 6 > Weight and Inertia Database

</center>

<br>
<p align="center">41

--------------------------------------------------------------------------
### 3. Electric Propulsion System Database
$\quad$ In the case of the propulsion system database, it contains information on the position and performance of the electric propulsion system of the eVTOL drone. The electric propulsion system of the eVTOL drone consists of a battery, an ESC, an electric motor, and a propeller. In the case of position, it represents the position of the electric motor connected to the propeller as the point of action of the thrust. The position database is as follows.

<center>

  ![< Graph 7 > Propulsion System Location Database](final%20image/graph7.png)
  
  < Chart 7 > Propulsion System Location Database

</center>

<br>
<p align="center">42

--------------------------------------------------------------------------
$\quad$ The battery is a PT-B10000-NSR35 product and has a capacity of 10,000 𝑚𝐴ℎ, the number of cells is 8, and the discharge rate is 35 𝐶. The voltage change according to the battery capacity is used in a table format, and the weight is set to 0 because it was considered in the weight and inertia database. As additional data, it has information on the cutoff voltage and the internal resistance of the battery in which the battery does not operate.

<center>

  ![< Graph 8 > Propulsion System Battery Database](final%20image/graph8.png)
  
  < Chart 8 > Propulsion System Battery Database

</center>

<br>
<p align="center">43

--------------------------------------------------------------------------
$\quad$ The ESC uses a FLAME-80A-12S product and, depending on the voltage, generates a PWM signal for driving an electric motor. The weight is set to 0 in consideration of the weight and inertia database, and includes range information of the generated PWM signal. As additional data, it contains information on the maximum minimum voltage, maximum current, and internal resistance.

<center>

  ![< Graph 9 > Propulsion System ESC Database](final%20image/graph9.png)
  
  < Chart 9 > Propulsion System ESC Database

</center>

<br>
<p align="center">44

--------------------------------------------------------------------------
$\quad$ The electric motor is a BLDC (Blushless Direct Current) motor and uses KDE5214XF product. The motor generates and rotates physical torque in response to the PWM signal transmitted from the ESC. The weight is included in the weight and inertia database and is set to 0, and the motor speed constant representing the number of revolutions according to voltage and the motor torque constant representing the torque according to current are included as information on the performance of the motor. Additionally, it contains information on an ideal current and voltage, and maximum current and internal resistance.

<center>

  ![< Graph 10 > Propulsion System Electic Motor Database](final%20image/graph10.png)
  
  < Chart 10 > Propulsion System Electic Motor Database
</center>

<br>
<p align="center">45

--------------------------------------------------------------------------
$\quad$ Torque generated by the electric motor rotates the propeller to generate the thrust and torque acting on the aircraft. The propeller used the XOAR-15x7 product, and a database considering the forward ratio was used as table-type data for the thrust and power coefficients. The propeller database contains the propeller's moment of inertia, diameter, and number of blades, and includes information on the geometric minimum and maximum pitch angle of the blade. The thrust and power coefficients are in the form of a table, according to the minimum rotational speed and the forward ratio representing the performance of the propeller. The independent variables of the two tables are the forward ratio, and the dependent variables are the thrust and power coefficients. In the case of a variable pitch propeller, a two-dimensional table can be used to represent the thrust and power coefficients according to the forward ratio and pitch angle. The following is an equation and database for thrust and power.

<center>

  ![< Graph 10 > Electic Propulsion System Propeller Database](final%20image/graph11.png)
  
  < Chart 11 > Electic Propulsion System Propeller Database
</center>

<br>
<p align="center">46

--------------------------------------------------------------------------

--------------------------------------------------------------------------

# 5. Analysis of Virtual Transition Flight Test Results for eVTOL Tiltrotor

$\quad$ In this chapter, an analysis of the test results for eVTOL Tiltrotor simulated transition flights is presented. Section 1 compares and analyzes the results using the existing PX4-Autopilot's transition flight algorithm and the results obtained by applying different transition flight schedules. Through this comparison, the aim is to assess the utility of the transition flight schedule derived from the trim analysis of the 3-degree-of-freedom dynamic model. Section 2 examines and analyzes the discrepancies between the interpretation results and the simulated flight test results.

## Section 1. Analysis of Virtual Transition Flight Test Results

$\quad$ This is an analysis of the transition flight algorithm applied to the existing flight control software and a different transition flight schedule. In this section, it can be confirmed that utilizing interpretation-based transition flight schedules ensures stability.

### 1. Comparison of Flight Status

$\quad$ For the state of transition flight, the state of flight such as altitude, flight distance, acceleration, speed, and pitch posture angle, which are longitudinal factors, will be analyzed. The following is an analysis of the virtual transition flight test results, and a blue vertical dotted line at 0 seconds means the start of the transition flight, and a red vertical dotted line at 7 seconds means the end of the transition flight. In order to confirm the recovery of the flight state after the transition flight, the 7-second area after the end of the transition flight was also analyzed.

<p align="center"> 62

-----------------------------------------------------------------------------------
<center>

![image 38](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/29f0cab8-8331-4d1c-9cb7-9b0768e1c516)

</center>

<p align="center"> < Picture 38 > Virtual Transition Flight Test Results Flight Distance Analysis

<center>

![image 39](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/5f5a0eab-bb2c-4b14-85fc-73505acaa345)

</center>

<p align="center">< Picture 39 > Virtual Transition Flight Test Results Flight Altitude Analysis

$\quad$ First, flight distance and altitude, which are longitudinal location components, were compared. In the case of flight distance, it was confirmed that the virtual transition flight test result of the existing PX4-Autopilot traveled the least, followed by the virtual transition flight test result applying the transition flight schedule, showing similar results, and it was confirmed that the transition flight test result flew farther than the existing flight algorithm.

<p align="center"> 63

-------------------------------------------------------

$\quad$ In the case of flight altitude, it can be observed that there is significant altitude loss in the virtual transition flight tests of the existing PX4-Autopilot. However, when applying transition flight schedules, a substantial reduction in altitude loss for the aircraft can be confirmed. Among these, it can be observed that case 𝐴, where the speed is smoothly varied, exhibits a more stable flight compared to case 𝐵. In case 𝐴, maintaining the attitude angle results in a similar and effective altitude maintenance compared to when the attitude angle is changing. In case 𝐵, it is evident that maintaining the attitude angle is more stable for flight than changing the attitude angle.

<center>

![image 40](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/049751d9-360e-4b64-95b5-351a0a61f117)

</center>

<p align="center"> < Picture 40 > Flight Speed Analysis of Virtual Transition Flight Test Results

<center>

![image 41](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/09854d14-d61e-4b6d-8c78-786fcfd152a8)

</center>

<p align="center"> < Picture 41 > Analysis of Flight Acceleration of Virtual Transition Flight Test Results

<p align="center"> 64

-----------------------------------------------------

$\quad$ In the case of the flight speed, the virtual transition flight test using the existing transition flight algorithm confirmed that the transition flight was terminated at low speed. For this reason, the transition to the fixed-wing flight mode was made after the transition flight, but due to the transition from the flight speed before the stall speed, insufficient lift was caused, resulting in a significant altitude loss, and at the same time, it fell down and the base of the aircraft went down. Conversely, the results of the virtual transition flight test using the transition flight schedule confirmed that the transition flight was converted to the fixed-wing flight mode after the stall speed. According to this effect, the aircraft has sufficient lift even after the mode transition, and through this, it can be confirmed that the mode is switched without significant altitude loss.

$\quad$ When the transition flight schedule is used, it can be seen that the transition rapidly converges to the target speed after the completion of the flight. However, it can be seen that all transition approaches the end of the flight and exceeds the target speed, except for the case of 𝐴_𝐶𝑜𝑛𝑠𝑡𝑎𝑛𝑡, which changes the speed smoothly and maintains a constant posture angle.

$\quad$ In the case of flight acceleration, when the existing transient flight algorithm is used, the magnitude of the acceleration is small, causing a stall because it cannot reach a sufficient flight speed within a time. On the other hand, in the case of a 𝐴 that changes the speed smoothly, it can be seen that the acceleration and deceleration are constant, and in the case of a 𝐵, it can be seen that the acceleration is slow and then decelerated rapidly.

<p align="center"> 65

------------------------------------------------------
<center>

![image 42](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/f6b128fd-44a5-49a9-817b-7048db49ff57)

</center>

<p align="center"> < Picture 42 > Pitch Angle Analysis of Virtual Transition Flight Test Results

$\quad$ 
In the case of the attitude angle during transition flight, virtual transition flight tests utilizing existing transition flight algorithms show that the attitude angle remains at 0 degrees during transition flight until the transition is completed, at which point it transitions to the fixed-wing flight mode. However, the aircraft descends due to insufficient flight speed at the end of transition, resulting in altitude loss. When using transition flight schedules, it is observed that the pitch attitude changes or is maintained according to the lift distribution ratio lead. However, as the transition flight progresses, the performance of the flight control system deteriorates due to the change in flight characteristics caused by the increase in flight speed, leading to a decrease in the performance of attitude control targeted after the end of transition. Additionally, it can be noted that the fixed-wing flight control system gradually controls the attitude after the transition flight is completed.

## 2. Flight Control Comparison

$\quad$ The purpose of this study is to analyze flight controls such as propeller tilt angle, tail control plane elevation angle, and front and rear motor throttle, which are longitudinal factors for transition flight control. The following is an analysis of flight test results, and a blue vertical dotted line at 0 seconds means the start of the transition flight and a red vertical dotted line at 7 seconds means the end of the transition flight. In order to confirm the change in flight control after the transition flight, the 7-second area after the end of the transition flight was also analyzed.

<p align="center"> 66

-----------------------------------------------------
<center>

![image 43](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/4f7ccbc0-746c-46c2-9e2b-cf268da5c884)

</center>

<p align="center"> < Picture 43 > Tilt Angle Analysis of Virtual Transition Flight Test Results
 
 <center>

![image 44](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/e55ad669-ceef-44ee-b13e-b7bc3f560dfb)

</center>

<p align="center"> < Picture 44 > Motor Control Analysis of Virtual Transition Flight Test Results

<p align="center"> 67

---------------------------------------------------
<center>

![image 45](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/bb335bb0-5127-4c55-8f6b-13c2f9628e20)

</center>

<p align="center"> < Picture 45 > Analysis of the Tail Control of the Virtual Transition Flight Test Results


$\quad$ First, by changing the propeller tilt angle, you can confirm the operation of the existing PX4 Autopilot transition flight algorithm and transition flight schedule algorithm. According to the transition flight schedule, in the case of a schedule that changes the pitch angle, it can be observed that the propeller tilt angle changes more rapidly.

$\quad$ The following is an analysis of motor throttle control results. In the existing transition flight algorithm, all motors are continuously utilized during transition flight, and it can be observed that in the second phase, the throttle of the rear motors gradually decreases. Due to this, the generated thrust from the rear decreases, resulting in an increase in thrust from the front. According to the transition flight schedule algorithm, after a certain period during transition flight, the aircraft does not use the rear motors and increases the throttle of the front motors.

<p align="center"> 68

------------------------------------------------------

The lack of thrust generated by the rear motor, which is not in use, results in insufficient thrust. This shortfall in thrust is compensated by utilizing the front motor.

$\quad$ In the case of tail control, it is associated with pitch angle control, and by controlling the tail control surface, the pitching moment generated by the wing is increased. It can be seen that the angle of the control surface is increased to increase the pitching moment in common during flight, and through this, it can be seen that the moment of raising the rider is generated. Here, it can be seen that the degree is small in the existing transition flight algorithm because the flight speed is not sufficient, so the moment occurring in the wing is not significant.

<p align="center"> 69

--------------------------------------------------------
## Section 2. Analysis of Transition Flight Schedule and Virtual Transition Flight Test Results

$\quad$ In this section, we will analyze the interpretation-based transitional flight schedule results and virtual transitional flight test results through flight simulations. Through this, we aim to analyze how well the controller in the flight simulation followed the transitional flight schedule and to what extent the results showed similarity. Depending on the speed schedule, we want to analyze the level of similarity in the results.

### 1. Speed Schedule A

$\quad$ The following is the transition flight test results for speed schedule 𝐴, which smoothly changes speed, depending on the thrust allocation ratio on the attitude control, maintaining the attitude angle or changing the attitude angle. A comparison was made for altitude, flight distance, speed, acceleration, and attitude angle changes during the transition flight schedule and the virtual transition flight test results. The following is a comparison graph.

<center>

![image 46](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/553d5a74-183f-4b64-96b4-a6243a8e4653)

</center>

<p align="center"> < Picture 46 > Comparison of Transition Flight Schedule 𝑨 and Virtual Flight Test Results

<p align="center"> 70

-----------------------------------------------------
<center>

![image 47](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/b6dab39b-3ae8-4971-b4bf-5b45ef14283a)

</center>

<p align="center"> < Picture 47 > Comparison of Flight Altitude with Transition Flight Schedule 𝑨 and Virtual Flight Test Results

<center>

![image 48](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/bb7e9a2f-e696-458d-ab4a-1727a48daf5c)

</center>

<p align="center"> < Picture 48 > Comparison of Flight Speed with Transition Flight Schedule 𝑨 and Virtual Flight Test Results

<center>

![image 49](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/54a628b7-8e90-4ad3-b201-a45c8b05868a)

</center>

<p align="center"> < Picture 49 > Comparison of Flight Accleration with Transition Flight Schedule 𝑨 and Virtual Flight Test Results

<p align="center"> 71

---------------------------------------------------

$\quad$ Through the analysis of the generated transitional flight schedule based on interpretation, it can be confirmed that virtual transitional flight test results exhibit a consistent trend. Depending on the characteristics of the speed schedule 𝐴, which smoothly varies the flight speed, it is observed that speed, acceleration, and flight distance change similarly. Among these, in the schedule that maintains the flight angle of attack, the changes are more stable, and it is confirmed that it shows a similar trend to the transitional flight schedule.

<center>

![image 50](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/5045c1a5-d80e-4f90-8b9e-4675c6621124)

</center>

<p align="center"> < Picture 50 > Comparison of Transition Flight Test Schedule and Virtual Transition Flight Test Results Pitch Angle

<p align="center"> 72

-------------------------------------------------------

$\quad$ It can be observed that, according to the pitch angle schedule of the transition flight, the aircraft is attempting to follow the set pitch attitude values received. However, there is an overall error, and this appears to be due to the limitations of the flight control system. It is evident that this error increases over time, and it seems to be a result of the lack of a separate controller tailored to the changing flight characteristics during the transition flight process between the multi-copter flight controller and the fixed-wing flight controller, based on the aircraft control system's switching structure.

### 2. Speed Schedule B

$\quad$ This is the virtual transition flight test result for the speed schedule 𝐵, which gradually changes speed and then rapidly decelerates, according to the lift distribution schedule. During the transition flight process, a comparison was made for altitude, flight distance, speed, acceleration, and changes in attitude angle between maintaining the attitude angle and changing it. The following are the comparison graphs.

<center>

![image 51](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/f47960b0-3eaa-4dbe-b8ea-f7e429632ae2)

</center>

<p align="center"> < Picture 51 > Comparison of Transition Flight Schedule 𝑩 and Virtual Transition Flight Test Results

<p align="center"> 73

---------------------------------------------------------
<center>

![image 52](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/7e12bd14-21b9-4252-b5f4-99bc1e054f6a)

</center>

<p align="center"> < Picture 52 > Comparison of Transition Flight Schedule 𝑩 and Virtual Transition Flight Altitude Test Results

<center>

![image 53](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/d13ce2b5-5b79-48a8-8478-0a88421f58ac)

</center>

<p align="center"> < Picture 53 > Comparison of Transition Flight Schedule 𝑩 and Virtual Transition Flight Speed Test Results

<center>

![image 54](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/076141ab-692a-4a70-a07a-13dca9a69941)

</center>

<p align="center"> < Picture 54 > Comparison of Transition Flight Schedule 𝑩 and Virtual Transition Flight Accleration Test Results

<p align="center"> 74

-------------------------------------------------------------

$\quad$ Through the interpretation of the generated transition flight schedule, it can be confirmed that the virtual transition flight test results tend to follow a trend. Depending on the characteristics of the speed schedule 𝐵, which involves gradually changing the flight speed and then rapidly decelerating, it can be observed that speed, acceleration, and flight distance undergo changes, but some errors are evident. Among these, schedules that maintain the flight pitch angle show a more stable evolution and exhibit a trend similar to the transition flight schedule.

<center>

![image 55](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/af2e3ad8-0d3b-4f98-b620-94403227b63c)

</center>

<p align="center"> < Picture 55 > Comparison of Transition Flight Schedule 𝑩 and Virtual Transition Pitch Attitude Test Results

<p align="center"> 75

----------------------------------------------------------

$\quad$ The flight control system receives pitch attitude setpoint values according to the transition flight schedule, aiming to track the specified pitch angles for the aircraft. However, there is a significant overall error, indicating limitations in the performance of the flight controller. This error tends to increase over time, suggesting that it may be attributed to the switching structure of the aircraft controller. Specifically, in the transition flight process between multi-copter flight control and fixed-wing flight control, there seems to be no separate controller to adapt to the changing flight characteristics, leading to the observed errors.

<p align="center"> 76

--------------------------------------------------------

# 6. Conclusion 

## Section 1. Conclusion

$\quad$ In this paper, a transition flight schedule for eVTOL tiltrotor aircraft was derived through trim analysis based on speed scheduling and lift distribution according to transition stability requirements. Additionally, an open-source flight control software and aerodynamic software were utilized to create a simulation environment tailored to the target aircraft. Virtual transition flight tests were conducted by applying the transition flight schedule in this simulated environment to ensure transition flight stability.

$\quad$ The applied transition flight schedule for virtual transition flight tests yielded four different schedules based on speed and lift coefficient contours. Commonly, in schedules where the flight pitch angle changes according to the lift coefficient contours, unstable results were observed compared to schedules that maintain a constant flight pitch angle. This is attributed to the inability of the attitude control system to guarantee performance in transition flight segments where flight characteristics change rapidly. Regarding the speed schedule, Schedule A, which smoothly accelerates and decelerates speed, demonstrated more stable results than Schedule B, which accelerates slowly and decelerates rapidly. The reason for this is that as the flight state changes rapidly during the transition flight process, the flight control system finds it challenging to track. Therefore, it can be concluded that an advantageous transition flight schedule involves smooth acceleration and deceleration of speed while maintaining a constant flight pitch angle.

$\quad$ Through this research, it has been confirmed that transition flight schedules generated at 3 degrees of freedom enhance flight stability even in a 6 degrees of freedom flight simulation environment. This validates the utility of transition flight scheduling. With this study, we anticipate achieving stable operations in the transition flight segments of eVTOL tiltrotor aircraft. Through the ongoing research of this kind, we hope to further explore the benefits of utilizing tiltrotor configurations.

<p align="center"> 77

-------------------------------------------------------

## Section 2. Future Plans

$\quad$ In this paper, a transition flight schedule for eVTOL tiltrotor aircraft was derived through interpretation. While the utility of the transition flight schedule was confirmed through virtual transition flight tests in a flight simulation environment, the performance of the flight controller was found to be insufficient due to the limitations of utilizing an open-source-based flight controller. In the future, to address these issues, a transition flight controller considering the flight characteristics varying with tilt angle and flight speed will be developed. The transition flight schedule will be applied, and stability will be verified through flight simulations. After confirming stability through flight simulations, practical flight tests using a physical aircraft will be conducted to validate the transition flight schedule and transition flight controller.

<p align="center"> 78

-----------------------------------------------------

