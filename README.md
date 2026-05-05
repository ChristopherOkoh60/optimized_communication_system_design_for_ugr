<h1>Optimization of a UGR Communication System</h1>


<h2>Description</h2>
This project utilizes a point-to-point type of communication system with multiple communication links between the Base Station (BS) and the UGR to establish connections one at a time based on stronger signal strength, and with feedback loops that enable the UGR to transmit data, video, and LiDAR sensor data back to the BS and receive commands for control, localization, and navigation. This project implemented intelligent communication adaptation and energy-efficient structure by designing the transmission of three communication network systems—LoRa (Long-Range device), Wi-Fi (Wireless Fidelity technology), and 5G (Fifth-Generation cellular network technology)—from a BS to the remote UGR deployed for Search and Rescue (SAR) operations. The Reinforcement Learning (RL) algorithm was developed to perform signal switching based on balance and stability, from networks with the lowest power consumption to networks with higher throughput.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Python</b>
- <b>Pandas</b>
- <b>PyTorch</b>
- <b>NumPy</b>

<h2>Environment</h2>

- <b>Wokwi</b>
- <b>Google Colab</b>

<h2>Project walk-through:</h2>
<b>(1)</b>
<b>Design a robust communication switching architecture utilizing multiple communication technologies (LoRa, Wi-Fi, and 5G) in real-time.</b>

- <b>For intelligent communication adaptation and energy-efficient networking in a SAR robot application, this project has been designed to include the transmission of three communication networks—LoRa, Wi-Fi, and 5G—from a base station to the field robot. </b>
- <b>These communication links support the robot’s performance for control, localization, navigation, and real-time data transmission. But due to inefficiencies depending on communication links, this design considers network communication switching based on signal strength using the RL algorithm. </b>

<p align="center">
Communication links (LoRa, Wi-Fi, 5G) Transmission <br/>
<img src="https://i.postimg.cc/XJ4x90gw/Picture2.png" height="30%" width="50%" alt="Disk Sanitization Steps"/>
<br />

<p align="center">
System Communication Architecture <br/>
<img src="https://i.postimg.cc/P5KFKJCH/Picture3.png" height="40%" width="60%" alt="Disk Sanitization Steps"/>
<br />

<p align="center">
Data generation through ESP32 MCU <br/>
<img src="https://i.postimg.cc/63YrMg0N/Screenshot-2026-05-05-130802.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />

<b>(2)</b>
<b>Implement a DQN model that will learn optimal communication decisions while interacting with the environment and cumulative rewards.</b>

- <b>The current state is fed into the network as the input, and it learns to estimate the Q values (corresponding to each action) for that state.</b>
- <b>The MCU collects state-transition tuples consisting of state (s), action (a), reward (r), and next state(s’) to interact and learn about the environment. </b>
- <b>The network is trained using the Bellman equation to approximate optimal Q-values, Q(s, a), enabling the MCU to learn the dynamic network switching through RL. </b>

<p align="center">
DQN Training Architecture: <br/>
<img src="https://i.postimg.cc/HkMs3M2y/1e2bc172-ac64-4815-97a4-5b3badd1f1f0i.png" height="60%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<b>Step 3</b>

- <b>Perform testing to ensure that the robot learned the trajectory pathway and obstacle detection</b>
- <b>Evaluate the testing outcomes</b>

<p align="center">
Results - (a) Action-Distribution, (b) Sensor Over Time, (c) Robot Motion Trajectory: <br/>
<img src="https://i.postimg.cc/Hs2GTq54/Screenshot-2026-05-05-022659.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
<br />

<b>Conclusion</b>

<b>This research project has applied the DQN model for buggy robot collision avoidance during autonomous navigation in a dynamic space. The robot effectively learned to move, avoid obstacles, and attempt the provided structured pathway based on sensor input and reward design. The trained outcome revealed that DQN’s efficiency is largely dependent on data quality, reward tuning, and system calibration.</b>




<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
