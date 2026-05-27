
# Multi-Sensor Data Fusion and Pattern Recognition for Intelligent Driving Systems

MS ECE Capstone Project - California State University, Fresno | Spring 2026

## Overview
This project builds a two-phase pipeline for autonomous driving. 
Phase 1 classifies the vehicle's motion state from sensor data. 
Phase 2 uses that classification to help a reinforcement learning 
agent tune a Kalman filter in real time. Both phases run on real 
driving data from the nuScenes dataset.

## What This Project Does
- Classifies vehicle motion into Stopped, Cruising, or Turning 
  using IMU, GPS, and Radar sensor features
- Uses a Hopfield Neural Network, Gradient Boosting, and Random 
  Forest for classification
- Passes the motion class directly into the RL agent's state space 
  as the 11th input dimension
- Adaptively tunes EKF, UKF, and Square-Root CKF noise parameters 
  using TD3, SAC, and PPO algorithms
- Detects and defends against GPS spoofing using NIS monitoring 
  and a parallel backup estimator

## Results
- 99.08% motion classification accuracy on real driving data
- 94.9% reduction in position estimation error with RL-adaptive filtering
- Maintained positioning accuracy under simulated GPS spoofing attacks

## Dataset
nuScenes v1.0-mini — 10 real driving scenes with synchronized 
IMU, GPS, and Radar data.
Download from: https://www.nuscenes.org/nuscenes

## How to Run

### 1. Install dependencies
pip install -r requirements.txt

### 2. Mount your dataset
Place the nuScenes v1.0-mini dataset in your Google Drive under:
/content/drive/MyDrive/Grad_Project_Dataset/v1.0-mini.tgz

### 3. Run the code
Open PROJECT_CONSOLIDATED.py in Google Colab and run all cells in order.

## Libraries Used
- Python 3.x
- PyTorch
- Scikit-learn
- NumPy
- Pandas
- Matplotlib
- nuScenes devkit

## Project Structure
multisensor-fusion-autonomous-driving/
│
├── PROJECT_CONSOLIDATED.py   # Full pipeline code
├── README.md                 # This file
├── requirements.txt          # Dependencies
└── figures/                  # Output plots (optional)

## Advisor
Dr. Shuo Wu — Assistant Professor, Dept. of ECE, CSU Fresno
