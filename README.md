<div align="center">

# Gabriel Calderon

**Embedded Systems Engineer | Computer Vision | Reinforcement Learning**

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&duration=3000&pause=1000&color=2E97F7&center=true&vCenter=true&width=700&lines=High-Performance+C%2B%2B+%7C+Real-Time+Systems;Reinforcement+Learning+%7C+Drone+Simulation;Computer+Vision+%7C+Object+Detection+%26+Tracking;Embedded+AI+%7C+Edge+Computing" alt="Typing SVG" />

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/gabriel-calderón-61b308214)
[![Email](https://img.shields.io/badge/Email-Contact-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:alvanezg1@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/chele-s)

</div>

---

## About Me

I am a **Systems Engineer** specializing in the intersection of **high-performance computing**, **computer vision**, and **reinforcement learning**. My work focuses on developing production-grade systems that bridge low-level hardware control with state-of-the-art AI algorithms.

**Core Competencies:**
- High-fidelity physics simulation with C++17 and Python interoperability via pybind11
- Deep Reinforcement Learning architectures (TD3, DDPG) with prioritized experience replay
- Real-time object detection using Transformer-based models (RF-DETR, DETR)
- Multi-object tracking with Extended Kalman Filters and probabilistic data association
- Embedded systems development on Raspberry Pi and custom hardware platforms
- GPU-accelerated inference pipelines with TensorRT and ONNX optimization

---

## Featured Projects

### Helix Drone — High-Fidelity Quadrotor Simulation

[![C++](https://img.shields.io/badge/C++-17-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)](https://github.com/chele-s)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://github.com/chele-s)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)](https://github.com/chele-s)
[![pybind11](https://img.shields.io/badge/pybind11-Bindings-blue?style=flat-square)](https://github.com/chele-s)

A research-grade quadrotor simulation platform designed for training autonomous flight controllers using deep reinforcement learning. The system combines a high-performance C++ physics core with a Python-based training pipeline.

<table>
<tr>
<td width="50%">

#### Physics Engine (C++)

- **6-DOF Rigid Body Dynamics**: Full Newton-Euler equations with quaternion-based attitude representation
- **Advanced Numerical Integration**: Runge-Kutta 4th order (RK4), RK45 adaptive step-size, Velocity Verlet
- **Rotor Aerodynamics**: Blade Element Theory with momentum theory coupling
- **Ground Effect Modeling**: Height-dependent thrust augmentation
- **Motor Dynamics**: First-order lag with ESC response characteristics, thermal modeling
- **Battery Simulation**: State-of-charge curves, voltage sag under load
- **Dryden Wind Model**: MIL-SPEC turbulence with configurable intensity

</td>
<td width="50%">

#### Training Pipeline (Python)

- **TD3/DDPG Agents**: Twin Delayed Deep Deterministic Policy Gradient implementation
- **Prioritized Experience Replay**: Sum-tree based sampling with importance weighting
- **Gymnasium Environment**: Configurable task types (hover, waypoint, trajectory tracking)
- **Domain Randomization**: Mass, inertia, motor constants, wind conditions
- **Curriculum Learning**: Progressive difficulty scaling for stable convergence
- **Vectorized Simulation**: Parallel environment execution for sample efficiency

</td>
</tr>
</table>

**Technical Highlights:**

```cpp
// High-performance physics with SIMD optimization and 64-byte alignment
class alignas(64) Quadrotor {
    void stepWithSubStepping(const MotorCommand& command, double agentDt);
    void stepAdaptive(const MotorCommand& command, double& dt);
    
    // Blade Element Theory thrust computation
    Vec3 computeTotalThrust() const noexcept;
    Vec3 computeAerodynamicForces(const Vec3& velocityBody) const noexcept;
    Vec3 computeGyroscopicTorque() const noexcept;
};
```

---

### GeoGauge — AI-Powered Road Damage Assessment

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://github.com/chele-s)
[![YOLO](https://img.shields.io/badge/YOLOv8-Detection-00FFFF?style=flat-square)](https://github.com/chele-s)
[![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)](https://github.com/chele-s)

An end-to-end system for automated pothole detection, depth estimation, and severity classification using monocular images. Designed for municipal infrastructure assessment and maintenance prioritization.

<table>
<tr>
<td width="50%">

#### Detection and Analysis

- **YOLOv8 Object Detection**: Fine-tuned for road damage classification
- **Depth Anything v2**: State-of-the-art monocular depth estimation
- **Multi-Backend Support**: Dynamic backend selection (Depth Anything v1/v2)
- **RANSAC Plane Fitting**: Ground plane estimation for metric depth calibration
- **Guided Filtering**: Edge-preserving depth map refinement

</td>
<td width="50%">

#### Severity Classification

- **Dimensional Analysis**: Length, width, and depth measurement from single images
- **Multi-Factor Scoring**: Combines geometric features with confidence maps
- **Priority Ranking**: Automated maintenance prioritization
- **Report Generation**: Detailed analysis with visualization overlays

</td>
</tr>
</table>

**Architecture:**

```python
class PotholeAnalyzer:
    def analyze_image(self, image_np_bgr: np.ndarray) -> List[Dict]:
        # Detection → Depth Estimation → Calibration → Classification
        detections = self._detect_potholes(image_rgb)
        depth_map = self._get_depth_map(image_rgb)
        results = self._process_detections(detections, depth_map, image_rgb)
        return results
```

---

### LiveCam AI — Real-Time Ball Detection and Tracking

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://github.com/chele-s)
[![RF-DETR](https://img.shields.io/badge/RF--DETR-Transformer-blueviolet?style=flat-square)](https://github.com/chele-s)
[![OpenCV](https://img.shields.io/badge/OpenCV-Tracking-5C3EE8?style=flat-square&logo=opencv&logoColor=white)](https://github.com/chele-s)

A low-latency ball tracking system for sports analytics, combining Transformer-based detection with probabilistic state estimation for robust tracking under occlusion and rapid motion.

<table>
<tr>
<td width="50%">

#### Detection Module

- **RF-DETR Backbone**: Region-focused Detection Transformer
- **Multi-Scale Inference**: Adaptive resolution for varying ball sizes
- **FP16 Inference**: Half-precision optimization for GPU acceleration
- **TensorRT Support**: Optional deployment-time optimization
- **Temporal Filtering**: Detection history for confidence smoothing

</td>
<td width="50%">

#### Tracking Module

- **Extended Kalman Filter**: 6-state model (position, velocity, acceleration)
- **Mahalanobis Gating**: Statistical outlier rejection
- **Adaptive Noise Estimation**: Dynamic process/measurement noise tuning
- **One-Euro Filter**: Jitter reduction with adaptive cutoff frequency
- **Hypothesis Management**: Multi-hypothesis tracking for ambiguous detections

</td>
</tr>
</table>

**Tracking Algorithm:**

```python
class ExtendedKalmanFilter:
    def predict(self, dt: Optional[float] = None) -> np.ndarray:
        # State transition with constant acceleration model
        # Dynamic F matrix construction based on actual dt
        
    def update(self, z: np.ndarray) -> np.ndarray:
        # Mahalanobis distance gating
        # Adaptive measurement noise based on detection confidence
```

---

## Technical Stack

<div align="center">

### Languages and Core Technologies

![C++](https://img.shields.io/badge/C++-17/20-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![CUDA](https://img.shields.io/badge/CUDA-12.x-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![CMake](https://img.shields.io/badge/CMake-Build-064F8C?style=for-the-badge&logo=cmake&logoColor=white)

### Machine Learning and AI

![PyTorch](https://img.shields.io/badge/PyTorch-2.x-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-Runtime-005CED?style=for-the-badge&logo=onnx&logoColor=white)
![TensorRT](https://img.shields.io/badge/TensorRT-Inference-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![Gymnasium](https://img.shields.io/badge/Gymnasium-RL-0081A5?style=for-the-badge)

### Computer Vision

![OpenCV](https://img.shields.io/badge/OpenCV-4.x-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Transformers](https://img.shields.io/badge/HuggingFace-Transformers-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)
![Ultralytics](https://img.shields.io/badge/Ultralytics-YOLO-00FFFF?style=for-the-badge)
![Supervision](https://img.shields.io/badge/Roboflow-Supervision-8338EC?style=for-the-badge)

### Embedded Systems and Hardware

![Raspberry Pi](https://img.shields.io/badge/Raspberry_Pi_5-A22846?style=for-the-badge&logo=raspberry-pi&logoColor=white)
![GPIO](https://img.shields.io/badge/GPIO-Hardware_PWM-8B0000?style=for-the-badge)
![pybind11](https://img.shields.io/badge/pybind11-C++/Python-blue?style=for-the-badge)

### DevOps and Tools

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![VS Code](https://img.shields.io/badge/VS_Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)

</div>

---

## Specializations

| Domain | Technologies | Applications |
|:-------|:-------------|:-------------|
| **Physics Simulation** | C++17, SIMD, Numerical Integration | Quadrotor dynamics, rigid body mechanics |
| **Reinforcement Learning** | TD3, DDPG, PPO, Gymnasium | Autonomous control, policy optimization |
| **Object Detection** | RF-DETR, YOLOv8, DETR | Sports analytics, infrastructure inspection |
| **State Estimation** | Kalman Filters, EKF, Particle Filters | Multi-object tracking, sensor fusion |
| **Depth Estimation** | Monocular depth, Stereo vision | 3D reconstruction, measurement systems |
| **Embedded AI** | TensorRT, ONNX, Raspberry Pi | Edge deployment, real-time inference |

---

## GitHub Analytics

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=chele-s&show_icons=true&theme=tokyonight&hide_border=true&include_all_commits=true&count_private=true" height="170" alt="GitHub Stats" />
<img src="https://github-readme-stats.vercel.app/api/top-langs?username=chele-s&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" height="170" alt="Top Languages" />

</div>

<div align="center">

<img src="https://github-readme-streak-stats.herokuapp.com/?user=chele-s&theme=tokyonight&hide_border=true" alt="GitHub Streak" />

</div>

<div align="center">

![](https://github-profile-trophy.vercel.app/?username=chele-s&theme=tokyonight&no-frame=true&no-bg=true&row=1&column=7)

</div>

---

## Contribution Activity

<div align="center">

<img src="https://github-readme-activity-graph.vercel.app/graph?username=chele-s&theme=tokyo-night&hide_border=true&custom_title=Contribution%20Graph" alt="Activity Graph" />

</div>

---

## Connect

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Gabriel_Calderon-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/gabriel-calderón-61b308214)
[![Email](https://img.shields.io/badge/Email-alvanezg1@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:alvanezg1@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-chele--s-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/chele-s)
[![Discord](https://img.shields.io/badge/Discord-Connect-7289DA?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/WXq9rx7P)

</div>

---

<div align="center">

### Contribution Graph

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/chele-s/chele-s/output/snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/chele-s/chele-s/output/snake.svg" />
  <img alt="GitHub Contribution Graph" src="https://raw.githubusercontent.com/chele-s/chele-s/output/snake.svg" />
</picture>

</div>

---

<div align="center">

**"Bridging the physical and digital worlds through high-performance simulation and intelligent systems."**

![Visitor Count](https://profile-counter.glitch.me/chele-s/count.svg)

<sub>El Salvador | Systems Engineer | Open to Collaboration</sub>

</div>
