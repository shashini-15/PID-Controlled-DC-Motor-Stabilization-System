## 🚀 PID-Controlled DC Motor Stabilization System

A real-time PID speed control system for a 12V brushed DC motor implemented using a Raspberry Pi 4, designed as part of IE3034 – Control Systems Engineering.

## 👥 Team & Module
Module: IE3034_CSE (Control Systems Engineering)
Student: L.A.S.S.S.Sampath (SLIIT | IT23619562)
Project Name: PID-Controlled DC Motor Stabilization System

## 📌 Project Overview

This project focuses on designing and implementing a closed-loop control system to stabilize the speed of a DC motor using a PID controller.

The system:

Models motor dynamics
Implements real-time PID control
Evaluates performance under disturbances
Demonstrates robustness across varying conditions

## 🎯 Objectives
Achieve fast and stable motor speed control
Minimize:
Overshoot ≤ 15%
Steady-state error ≤ 2%
Ensure no sustained oscillations
Optimize settling time

## ⚙️ System Architecture
Controller: Raspberry Pi 4
Motor Driver: L298N H-Bridge
Motor: 12V DC Motor with Encoder
Feedback: Quadrature Encoder (150 PPR)
Control Method: PWM-based PID control

## 🧠 Control Strategy
PID Controller

The system uses a discrete PID controller:

Kp = 0.18
Ki = 0.06
Kd = 0.10

Features:

Anti-windup protection
Derivative noise filtering
Base PWM to overcome motor deadband
Overspeed safety cut-off

## 📊 Key Results
Metric	Value
Settling Time	~17.2 s
Overshoot	4.27%
Steady-State Error	0.75%
Stability	✅ No oscillations

## 🔬 System Modeling

The motor is approximated as a first-order system:

V(s)
ω(s)
	​

=
0.40s+1
1.69
	​


Where:

Time constant (τ) = 0.40 s
DC gain = 1.69 RPM/%

## 🔧 Features
✅ Real-time PID control in Python
✅ Interrupt-based encoder reading
✅ Noise filtering (EMA + Moving Average)
✅ Disturbance rejection capability
✅ Robust to ±10% voltage variation
✅ Custom PCB implementation

## 🧪 Testing & Validation
✔ Setpoint Tracking
Tested at: 130 RPM, 150 RPM, 170 RPM
Maintained stable performance across all
✔ Disturbance Rejection
Recovers from sudden load disturbance in 8–10 seconds
✔ Voltage Variation
Stable under:
10.8V (-10%)
12V (nominal)
13.2V (+10%)

## 🧩 Hardware Design

Custom PCB includes:

Overcurrent protection (fuses)
Decoupling capacitors
PWM noise filtering
Voltage divider (5V → 3.3V for GPIO safety)

## 🖥️ Software
Language: Python
Platform: Raspberry Pi OS
Control Loop:
Sampling time = 0.2 s
PWM frequency = 1000 Hz

## 👥 Team Members
Gunarathne M.
Samaradiwakara K.D.M.M.S.
Perera L.I.D.
Dissanayake D.M.D.C.
Sampath L.A.S.S.S.

## 📁 Project Structure 
PID-Motor-Control/
├── main.py                 # Main control loop (PID execution)
├── pid_controller.py       # PID algorithm implementation
├── encoder.py              # Encoder pulse reading & RPM calculation
├── motor_driver.py         # Motor control (PWM & direction)
├── config.py               # System parameters (Kp, Ki, Kd, dt, etc.)
├── utils.py                # Filtering & helper functions
├── requirements.txt        # Dependencies
└── README.md               # Project documentation

## 📌 Conclusion

This project demonstrates that a well-tuned PID controller on low-cost embedded hardware can achieve:

High accuracy
Strong robustness
Reliable real-time performance

## 📜 License

This project is for academic purposes.
