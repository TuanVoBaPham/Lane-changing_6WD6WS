**Autonomous Vehicle Lane-Changing Control**
-----
**Sliding Mode Control (SMC) with Extended State Observer (ESO)**

This repository contains Simulink simulation models for an autonomous vehicle lane-change control project using Sliding Mode Control (SMC) combined with an Extended State Observer (ESO).
<br>
The project focuses on robust lateral vehicle control during lane-change maneuvers under modeling uncertainties and external disturbances.

**Trajectory & Reference Generation (y_d, psi_d)**

These blocks generate the reference lateral trajectory (y_d) and the desired yaw rate (psi_d).

**Error Block (ERROR)**

Defines the tracking errors between the reference signals and the actual vehicle states.
<br>
Computes: Lateral position error, Yaw rate tracking error
<br>
The error signals are used as inputs to the Extended State Observer (ESO).

**Extended State Observer (ESO)**

Simulates the Extended State Observer.
<br>
Estimates: Unmeasured system states, Lumped disturbances and model uncertainties
<br>
Provides estimated states and disturbance terms to enhance robustness of the controller.

**Controller Block (Controller)**

Implements the Sliding Mode Control (SMC) algorithm.
<br>
Uses: Tracking errors, ESO-estimated states and disturbances
<br>
Generates control inputs to ensure robust lane-change tracking under uncertainties.

**Vehicle Plant Model (Plant)**

Represents the dynamic model of a 6-wheel-drive / 6-wheel-steering (6WD/6WS) vehicle.
<br>
Simulates the vehicle response to steering commands.
<br>
Outputs vehicle states such as lateral motion and yaw dynamics.

**Control Signal Converter (Converter)**

Converts the controller outputs into three steering angles:
<br>
Front steering angle
<br>
Middle steering angle
<br>
Rear steering angle
