# **CRESSim Autonomous Suction — Unity Simulation Environment**  
*A modified CRESSim Unity environment supporting autonomous surgical suction, blood pooling, and ROS 2 integration.*

## **Overview**
This repository contains the **Unity simulation environment** used to develop and evaluate autonomous surgical suction behaviours.  
It is built on top of **CRESSim**, a high‑fidelity surgical robotics simulator, and includes custom modifications to support:

- Blood pooling and fluid accumulation  
- Suction tool behaviour and particle removal  
- Enhanced tool–tissue interaction  
- Real‑time communication with ROS 2 via ROS–TCP Endpoint  

This repository provides the **simulation half** of the system.  
The **ROS 2 autonomy workspace** lives separately:

**ROS 2 Autonomy Repository**  
[https://github.com/el22mf/ros2-autonomous-suction](https://github.com/el22mf/ros2-autonomous-suction)

---

## **System Architecture**
The full system is split across two repositories:

### **This repository (Unity / CRESSim)**
- Modified CRESSim environment  
- Blood pooling simulation  
- Suction tool behaviour scripts  
- Unity scene setup  
- ROS–TCP Endpoint configuration  
- PhysX‑based interaction  

### **ROS 2 repository**
- Perception (blood detection)  
- Suction behaviour logic  
- Motion planning  
- ROS–Unity bridge  
- Launch files  

The two communicate over TCP using the **ROS–TCP Endpoint** package.

---

## **Requirements**

### **Software**
- Unity **2022.3 LTS** (recommended)  
- CRESSim (included in this project)  
- ROS–TCP Endpoint (Unity package)  
- ROS 2 Humble or Iron (for the ROS 2 repo)

### **Hardware**
- GPU recommended for real‑time simulation  
- PhysX 5 compatible environment  

---

## **Setup**

### **1. Clone the repository**
```
git clone https://github.com/el22mf/CRESSim-autonomous-suction
```

### **2. Open the project in Unity**
- Open Unity Hub  
- Select **Open Project**  
- Choose this folder  
- Allow Unity to import all assets (first load may take several minutes)

### **3. Install ROS–TCP Endpoint**
In Unity:

1. Open **Window → Package Manager**  
2. Add package from Git URL:  
   ```
   https://github.com/Unity-Technologies/ROS-TCP-Endpoint.git
   ```
3. Ensure **ROS 2 mode** is enabled in the ROS–TCP Endpoint component

### **4. Load the simulation scene**
Open:

```
Assets/Scenes/SuctionSimulation.unity
```

This scene contains:

- Blood pooling environment  
- Suction tool  
- CRESSim surgical table  
- ROS bridge objects  

---

## **Running the Simulation**

### **1. Start ROS 2 nodes**
In the ROS 2 repo:

```
ros2 launch suction_system bringup.launch.py
```

### **2. Press Play in Unity**
- The simulation begins  
- Blood pooling events are published to ROS 2  
- The suction tool receives autonomous commands from ROS 2  

---

## **Features**
- Real‑time blood pooling simulation  
- Custom suction tool behaviour  
- PhysX‑based particle removal  
- ROS–Unity communication  
- Modular CRESSim extensions  
- Designed for surgical autonomy research  

---

## **Related Repositories**
- **ROS 2 Autonomy Workspace**  
  [https://github.com/el22mf/ros2-autonomous-suction](https://github.com/el22mf/ros2-autonomous-suction)

- **Original CRESSim**  
  [https://github.com/tbs-ualberta/CRESSim](https://github.com/tbs-ualberta/CRESSim)

- **ROS–TCP Endpoint**  
  [https://github.com/Unity-Technologies/ROS-TCP-Endpoint](https://github.com/Unity-Technologies/ROS-TCP-Endpoint)


---

## **Author**
**Matthew Foster**  
MEng Mechatronics & Robotics Engineering  
University of Leeds  
