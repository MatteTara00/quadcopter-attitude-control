# Quadcopter Attitude Control

## Overview
This project focuses on the modeling, control, and validation of a quadcopter UAV, including both simulation and real-world implementation. Multiple control strategies are developed and evaluated for attitude stabilization under realistic conditions.

The workflow spans the full development pipeline: nonlinear modeling, simulation with noise characterization, and deployment on a PX4-based flight controller via Simulink Coder.

---

## Contributions

- Nonlinear modeling of quadcopter dynamics (simplified and high-fidelity models)  
- Design and implementation of control strategies for attitude stabilization (including LQR, PID, and nonlinear approaches)  
- Development of state estimation algorithms based on Extended Kalman Filter (EKF)  
- Integration of control algorithms in Simulink and preparation for real-time deployment on PX4  

---

## Project Structure

The repository is organized into two main sections:

### 📂 Simulation
This folder contains the simulation environment used for controller design and validation.

Each controller-specific subfolder includes:
- `init_control.m` — initialization script (must be run before simulations)  
- Simulink models for different scenarios:
  - `controller_no_noise.slx` — ideal (noiseless) conditions  
  - `controller_with_noise_control.slx` — noisy simulation using a custom quadcopter model  
  - `controller_with_noise_realistic.slx` — realistic simulation using PX4 model  

Key features:
- Custom nonlinear quadcopter model derived from first-principles modeling  
- Integration of realistic noise profiles based on experimental data  
- Comparison between simplified and high-fidelity PX4 dynamics  

#### 📂 Noise
Contains tools for:
- extracting noise characteristics from experimental data  
- EKF design and validation  

---

### 📂 Real System
This folder contains the implementation deployed on the real UAV.

Each controller-specific subfolder includes:
- `init_control.m` — initialization script  
- `controller_HW.slx` — controller without filtering  
- `controller_HW_EKF.slx` — controller with EKF-based state estimation  

Key features:
- Code generation via Simulink Coder  
- Deployment on PX4 flight controller  
- Real-world validation of control strategies  

---

## Workflow

The project follows a structured development pipeline:

1. System modeling (simplified + PX4-based models)  
2. Controller design and simulation  
3. Noise characterization and EKF-based state estimation  
4. Code generation via Simulink Coder  
5. Deployment on PX4 flight controller  
6. Experimental validation on real platform  

---

## Requirements

- MATLAB / Simulink  
- Simulink Coder  
- PX4 development environment  

---

## Usage

1. Navigate to the desired controller folder  
2. Run `init_control.m`  
3. Open the corresponding Simulink model  
4. Choose simulation or real-system configuration  

---

## Notes

- Simulation includes both simplified and high-fidelity models  
- Real-system implementation interfaces directly with PX4  
- EKF is used for state estimation under noisy measurements  
- Always run initialization scripts before executing models  

---
