#  1. Introduction 

## Section 1. Research Background
$\quad$ In this study, we explain the necessity of transition flight scheduling for eVTOL tiltrotor aircraft.

###  $\quad$ 1. (UAM - Urban Air Mobility)

$\quad$ As civilization progresses worldwide and populations increase, there's a deepening concentration of people in major cities, evolving them into mega-cities. These urban areas face significant economic losses due to congestion in surface transportation, surpassing the two-dimensional limits of conventional urban transport. This has led to serious environmental issues, prompting the necessity for innovative transportation solutions.

$\quad$ The urban air mobility (UAM) is proposed as a solution to extend urban transportation from 2D to 3D, and it has garnered significant research and investment from industries and research institutions to address numerous challenges in enabling flights within densely populated city areas.

$\quad$ For safe flights in urban areas, ensuring flight stability is crucial while also employing propulsion systems that generate minimal noise to reduce urban noise levels. Additionally, using environmentally friendly energy sources to prevent environmental issues is essential. To operate in urban areas without runways, it needs to be capable of vertical takeoff and landing (VTOL). To address these challenges, electric Vertical Takeoff and Landing (eVTOL) aircraft have emerged.

<p align="center"> 1

------------------------------------------------------------------------

###  $\quad$ 2. eVTOL (electric Vertical Takeoff & Landing) Tiltrotor

$\quad$ eVTOL stands for electric Vertical Takeoff and Landing aircraft, which are capable of vertical takeoff and landing using electric propulsion systems. These aircraft generate thrust in the vertical direction, enabling them to perform vertical takeoffs and landings. eVTOLs that can perform vertical takeoffs do not require a separate runway, making them suitable for urban air mobility or unmanned drone systems.

$\quad$ eVTOL aircraft are designed to be powered by electricity, offering lower carbon emissions compared to conventional aircraft using fossil fuels, as well as reduced noise pollution and potentially lower operational costs. These eVTOLs come in three main configurations: Multirotor, Lift & Cruise, and Tiltrotor.

$\quad$ Among these, the Tiltrotor configuration can vertically take off by orienting the propellers in the vertical direction of the aircraft, allowing it to fly like a helicopter. During cruise, the propellers can be oriented horizontally, enabling the aircraft to fly like a fixed-wing airplane. The Tiltrotor configuration combines the advantages of both helicopter and fixed-wing aircraft, making it a subject of active research in various research institutions and industries recently.

$\quad$ Tiltrotor aircraft have a unique flight phase called transition flight, where the direction of the propellers is changed to alter the flight mode. During transition flight in a tiltrotor aircraft, the thrust direction of the propellers changes, leading to a transformation in the aircraft's configuration and a complex variation in its flight characteristics. Consequently, the transition flight phase of a tiltrotor aircraft is considered highly unstable, posing challenges that necessitate research to ensure flight safety and guarantee the secure operation of tiltrotor aircraft.

<p align="center"> 2

-----------------------------------------------------------------------

## Section 2. Analysis of Existing Similar Studies

$\quad$ Numerous studies are underway to ensure the flight stability during transition phases, which are inherently unstable, for the operation of safe eVTOL tiltrotor aircraft. In this section, we analyze existing similar research on securing the transitional flight stability of eVTOL tiltrotor aircraft and present the limitations of these studies, clearly establishing the need for our research.

### $\quad$ 1. Interpretative Study in Performance of Transition Flight Area

$\quad$ In a paper authored at NASA Ames Research Center, an analysis was conducted to understand the flight complexity of tiltrotor aircraft by examining the airspeed and flight path angle or vertical velocity at various flight regimes based on propeller tilt angles. To achieve this, longitudinal flight dynamics modeling of Bell's XV-15 was employed. Trim analysis was conducted based on flight speed and propeller tilt angles to analyze the regions where stable flight was feasible.

<p align="center">
 
 ![< image > Shape Database](final%20image/image1.png)

</p>


 <p align="center"> 
 < Picture 1 > Transition Corridor for Various Rotor Tilt Angels


 <p align="center"> 3

--------------------------------------------------------------------------

 ### 2. Research on Transition Flight Control


 $\quad$ In a paper from the University of Cranfield in the UK, the longitudinal flight control system of an eVTOL tiltrotor aircraft was developed. In this process, instead of manipulating the propeller tilt angle, the pilot adjusted the flight speed using minimal power curves and numerical optimization to determine the optimal tilt schedule. To achieve this, trim analysis of the aircraft's performance was conducted, utilizing this information to assess the feasible flight envelope based on propeller tilt angles and determining the optimal tilt schedule.

$\quad$ Afterward, following the optimal slope schedule, specifying trim points for linearization, and gain scheduling along the linearized points of the PID controller, we designed the controller. Through this controller, when adjusting the desired speed, the controller gain values and propeller tilt angles automatically change, enabling flight



 ![< image > Shape Database](final%20image/image2.png)


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
 ![< image > Shape Database](final%20image/image3.png)

<p align="center">  < Picture 3 > Overall research process architecture

<p align="center"> 7

---------------------------------------------------------------------------------

# 5. Analysis of Virtual Transition Flight Test Results for eVTOL Tiltrotor

$\quad$ In this chapter, an analysis of the test results for eVTOL Tiltrotor simulated transition flights is presented. Section 1 compares and analyzes the results using the existing PX4-Autopilot's transition flight algorithm and the results obtained by applying different transition flight schedules. Through this comparison, the aim is to assess the utility of the transition flight schedule derived from the trim analysis of the 3-degree-of-freedom dynamic model. Section 2 examines and analyzes the discrepancies between the interpretation results and the simulated flight test results.

## Section 1. Analysis of Virtual Transition Flight Test Results

$\quad$ This is an analysis of the transition flight algorithm applied to the existing flight control software and a different transition flight schedule. In this section, it can be confirmed that utilizing interpretation-based transition flight schedules ensures stability.

### 1. Comparison of Flight Status

$\quad$ For the state of transition flight, the state of flight such as altitude, flight distance, acceleration, speed, and pitch posture angle, which are longitudinal factors, will be analyzed. The following is an analysis of the virtual transition flight test results, and a blue vertical dotted line at 0 seconds means the start of the transition flight, and a red vertical dotted line at 7 seconds means the end of the transition flight. In order to confirm the recovery of the flight state after the transition flight, the 7-second area after the end of the transition flight was also analyzed.

<p align="center"> 62

-----------------------------------------------------------------------------------

![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/29f0cab8-8331-4d1c-9cb7-9b0768e1c516)



<p align="center"> < Picture 38 > Virtual Transition Flight Test Results Flight Distance Analysis

![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/5f5a0eab-bb2c-4b14-85fc-73505acaa345)


<p align="center">< Picture 39 > Virtual Transition Flight Test Results Flight Altitude Analysis

$\quad$ First, flight distance and altitude, which are longitudinal location components, were compared. In the case of flight distance, it was confirmed that the virtual transition flight test result of the existing PX4-Autopilot traveled the least, followed by the virtual transition flight test result applying the transition flight schedule, showing similar results, and it was confirmed that the transition flight test result flew farther than the existing flight algorithm.

<p align="center"> 63

-------------------------------------------------------

$\quad$ In the case of flight altitude, it can be observed that there is significant altitude loss in the virtual transition flight tests of the existing PX4-Autopilot. However, when applying transition flight schedules, a substantial reduction in altitude loss for the aircraft can be confirmed. Among these, it can be observed that case 𝐴, where the speed is smoothly varied, exhibits a more stable flight compared to case 𝐵. In case 𝐴, maintaining the attitude angle results in a similar and effective altitude maintenance compared to when the attitude angle is changing. In case 𝐵, it is evident that maintaining the attitude angle is more stable for flight than changing the attitude angle.


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/049751d9-360e-4b64-95b5-351a0a61f117)

<p align="center"> < Picture 40 > Flight Speed Analysis of Virtual Transition Flight Test Results


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/09854d14-d61e-4b6d-8c78-786fcfd152a8)

<p align="center"> < Picture 41 > Analysis of Flight Acceleration of Virtual Transition Flight Test Results

<p align="center"> 64

-----------------------------------------------------

$\quad$ In the case of the flight speed, the virtual transition flight test using the existing transition flight algorithm confirmed that the transition flight was terminated at low speed. For this reason, the transition to the fixed-wing flight mode was made after the transition flight, but due to the transition from the flight speed before the stall speed, insufficient lift was caused, resulting in a significant altitude loss, and at the same time, it fell down and the base of the aircraft went down. Conversely, the results of the virtual transition flight test using the transition flight schedule confirmed that the transition flight was converted to the fixed-wing flight mode after the stall speed. According to this effect, the aircraft has sufficient lift even after the mode transition, and through this, it can be confirmed that the mode is switched without significant altitude loss.

$\quad$ When the transition flight schedule is used, it can be seen that the transition rapidly converges to the target speed after the completion of the flight. However, it can be seen that all transition approaches the end of the flight and exceeds the target speed, except for the case of 𝐴_𝐶𝑜𝑛𝑠𝑡𝑎𝑛𝑡, which changes the speed smoothly and maintains a constant posture angle.

$\quad$ In the case of flight acceleration, when the existing transient flight algorithm is used, the magnitude of the acceleration is small, causing a stall because it cannot reach a sufficient flight speed within a time. On the other hand, in the case of a 𝐴 that changes the speed smoothly, it can be seen that the acceleration and deceleration are constant, and in the case of a 𝐵, it can be seen that the acceleration is slow and then decelerated rapidly.

<p align="center"> 65

------------------------------------------------------


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/f6b128fd-44a5-49a9-817b-7048db49ff57)

<p align="center"> < Picture 42 > Pitch Angle Analysis of Virtual Transition Flight Test Results

$\quad$ 
In the case of the attitude angle during transition flight, virtual transition flight tests utilizing existing transition flight algorithms show that the attitude angle remains at 0 degrees during transition flight until the transition is completed, at which point it transitions to the fixed-wing flight mode. However, the aircraft descends due to insufficient flight speed at the end of transition, resulting in altitude loss. When using transition flight schedules, it is observed that the pitch attitude changes or is maintained according to the lift distribution ratio lead. However, as the transition flight progresses, the performance of the flight control system deteriorates due to the change in flight characteristics caused by the increase in flight speed, leading to a decrease in the performance of attitude control targeted after the end of transition. Additionally, it can be noted that the fixed-wing flight control system gradually controls the attitude after the transition flight is completed.

## 2. Flight Control Comparison

$\quad$ The purpose of this study is to analyze flight controls such as propeller tilt angle, tail control plane elevation angle, and front and rear motor throttle, which are longitudinal factors for transition flight control. The following is an analysis of flight test results, and a blue vertical dotted line at 0 seconds means the start of the transition flight and a red vertical dotted line at 7 seconds means the end of the transition flight. In order to confirm the change in flight control after the transition flight, the 7-second area after the end of the transition flight was also analyzed.

<p align="center"> 66

-----------------------------------------------------


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/4f7ccbc0-746c-46c2-9e2b-cf268da5c884)


<p align="center"> < Picture 43 > Tilt Angle Analysis of Virtual Transition Flight Test Results
 

![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/e55ad669-ceef-44ee-b13e-b7bc3f560dfb)


<p align="center"> < Picture 44 > Motor Control Analysis of Virtual Transition Flight Test Results

<p align="center"> 67

---------------------------------------------------


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/bb335bb0-5127-4c55-8f6b-13c2f9628e20)


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


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/553d5a74-183f-4b64-96b4-a6243a8e4653)


<p align="center"> < Picture 46 > Comparison of Transition Flight Schedule 𝑨 and Virtual Flight Test Results

<p align="center"> 70

-----------------------------------------------------


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/b6dab39b-3ae8-4971-b4bf-5b45ef14283a)

<p align="center"> < Picture 47 > Comparison of Flight Altitude with Transition Flight Schedule 𝑨 and Virtual Flight Test Results


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/bb7e9a2f-e696-458d-ab4a-1727a48daf5c)

<p align="center"> < Picture 48 > Comparison of Flight Speed with Transition Flight Schedule 𝑨 and Virtual Flight Test Results


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/54a628b7-8e90-4ad3-b201-a45c8b05868a)


<p align="center"> < Picture 49 > Comparison of Flight Accleration with Transition Flight Schedule 𝑨 and Virtual Flight Test Results

<p align="center"> 71

---------------------------------------------------

$\quad$ Through the analysis of the generated transitional flight schedule based on interpretation, it can be confirmed that virtual transitional flight test results exhibit a consistent trend. Depending on the characteristics of the speed schedule 𝐴, which smoothly varies the flight speed, it is observed that speed, acceleration, and flight distance change similarly. Among these, in the schedule that maintains the flight angle of attack, the changes are more stable, and it is confirmed that it shows a similar trend to the transitional flight schedule.

![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/5045c1a5-d80e-4f90-8b9e-4675c6621124)

<p align="center"> < Picture 50 > Comparison of Transition Flight Test Schedule and Virtual Transition Flight Test Results Pitch Angle

<p align="center"> 72

-------------------------------------------------------

$\quad$ It can be observed that, according to the pitch angle schedule of the transition flight, the aircraft is attempting to follow the set pitch attitude values received. However, there is an overall error, and this appears to be due to the limitations of the flight control system. It is evident that this error increases over time, and it seems to be a result of the lack of a separate controller tailored to the changing flight characteristics during the transition flight process between the multi-copter flight controller and the fixed-wing flight controller, based on the aircraft control system's switching structure.

### 2. Speed Schedule B

$\quad$ This is the virtual transition flight test result for the speed schedule 𝐵, which gradually changes speed and then rapidly decelerates, according to the lift distribution schedule. During the transition flight process, a comparison was made for altitude, flight distance, speed, acceleration, and changes in attitude angle between maintaining the attitude angle and changing it. The following are the comparison graphs.


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/f47960b0-3eaa-4dbe-b8ea-f7e429632ae2)


<p align="center"> < Picture 51 > Comparison of Transition Flight Schedule 𝑩 and Virtual Transition Flight Test Results

<p align="center"> 73

---------------------------------------------------------


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/7e12bd14-21b9-4252-b5f4-99bc1e054f6a)


<p align="center"> < Picture 52 > Comparison of Transition Flight Schedule 𝑩 and Virtual Transition Flight Altitude Test Results


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/d13ce2b5-5b79-48a8-8478-0a88421f58ac)


<p align="center"> < Picture 53 > Comparison of Transition Flight Schedule 𝑩 and Virtual Transition Flight Speed Test Results


![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/076141ab-692a-4a70-a07a-13dca9a69941)

<p align="center"> < Picture 54 > Comparison of Transition Flight Schedule 𝑩 and Virtual Transition Flight Accleration Test Results

<p align="center"> 74

-------------------------------------------------------------

$\quad$ Through the interpretation of the generated transition flight schedule, it can be confirmed that the virtual transition flight test results tend to follow a trend. Depending on the characteristics of the speed schedule 𝐵, which involves gradually changing the flight speed and then rapidly decelerating, it can be observed that speed, acceleration, and flight distance undergo changes, but some errors are evident. Among these, schedules that maintain the flight pitch angle show a more stable evolution and exhibit a trend similar to the transition flight schedule.

![image](https://github.com/KU-SanghoLee/Master-s-paper-Translate-Undergraduate-Students/assets/155501841/af2e3ad8-0d3b-4f98-b620-94403227b63c)


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



<p align="center">
  <img width="400" height="350" src= img/image2.png>
</p>
