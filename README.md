# Franka Emika Robot Setup and Simulation Guide

This guide provides step-by-step instructions to set up and operate the Franka Emika robots (Paperino Franka and Topolino Franka) in the lab. Follow these steps to ensure proper startup, configuration, and execution of simulations with the robots and Movella Xsens IMUs.

---

## 1. Startup

1. **Turn on the Robot**
   - Power on the robot using the appropriate switches.

2. **Connect to the Robot**
   - Access the robot's interface by navigating to one of the following IP addresses on the connected Ethernet network:
     - **Paperino Franka**: `172.16.0.3`
     - **Topolino Franka**: `172.16.0.4`

3. **Log In**
   - Enter the robot interface using your assigned username and password.

4. **Unlock Joints**
   - Unlock the robot’s joints. _(Note: This process may require several attempts.)_

5. **Activate FCI**
   - Enable the Franka Control Interface (FCI) and confirm communication with ROS.

---

## 2. Move the Robot to Home Configuration

Run the following command to reset the robot to its home position:

```bash
roslaunch franka_example_controllers move_to_start.launch robot_ip:=172.16.0.3
```

- Replace `172.16.0.3` with the appropriate IP if using Topolino Franka.
- _(Note: This step may require multiple attempts to complete successfully.)_

---

## 3. Demo with Movella Xsens IMUs

### Setup

1. Navigate to the appropriate workspace:

```bash
cd haria_ros/haria_ws
source devel/setup.bash
cd experiment_execution
```

2. Check available folders:

```bash
ls
```

You should see the following folders:
- `cogripper`
- `6th_finger`
- `robot`

3. Navigate to the `robot` folder and check for available scenarios:

```bash
cd robot
ls
```

Choose between the `continuous` or `discrete` scenario for either the **pot** or **pouring** tasks.

### Important Notes

- **Use the following IMUs:**
  - IMUs **1, 2, 3, and 5**. Do **not** use IMU 4.

- **IMU Positioning:**
  - `2`: Hand
  - `3`: Forearm
  - `1`: Arm
  - `5`: Chest

---

### 🚀 You're all set!
Follow these steps carefully to ensure smooth operation and execution. If you encounter any issues, double-check connections and settings before retrying.

