<div align="center">

<!-- Animated Header with Gradient Effect -->
<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:1a1a2e,100:16213e&height=200&section=header&text=Gabriel%20Calderón&fontSize=60&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=Embedded%20Systems%20%7C%20Computer%20Vision%20%7C%20Reinforcement%20Learning&descAlignY=55&descSize=18"/>

<!-- Dynamic Tech Animation -->
<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=24&duration=2500&pause=800&color=58A6FF&center=true&vCenter=true&multiline=true&repeat=true&width=900&height=100&lines=High-Performance+C%2B%2B17+%7C+Real-Time+Physics+Simulation+%7C+SIMD+Optimization;Deep+Reinforcement+Learning+%7C+TD3%2FDDPG+%7C+Curriculum+Learning;Transformer-Based+Detection+%7C+RF-DETR+%7C+Extended+Kalman+Filtering" alt="Typing SVG" />

<!-- Professional Social Links with Animated Hover -->
<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white&link=https://www.linkedin.com/in/gabriel-calderón-61b308214)](https://www.linkedin.com/in/gabriel-calderón-61b308214)
[![Email](https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:alvanezg1@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/chele-s)
[![Discord](https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/WXq9rx7P)

<br/>

<!-- Animated Skill Icons -->
<p>
<img src="https://skillicons.dev/icons?i=cpp,python,pytorch,cuda,opencv,docker,linux,git,cmake,raspberrypi&perline=10&theme=dark" alt="Skills"/>
</p>

</div>

<br/>

<!-- Section Divider -->
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" width="100%">

## About

I architect **production-grade systems** at the intersection of **low-level hardware control** and **state-of-the-art machine learning**. My expertise spans from optimizing C++ physics engines with SIMD instructions to deploying Transformer-based detection models on edge devices.

<table>
<tr>
<td width="50%">

### Core Engineering

- **C++17/20** with template metaprogramming and SIMD vectorization
- **pybind11** for seamless C++/Python interoperability
- **Numerical Methods**: RK4, RK45 adaptive integration, quaternion kinematics
- **Memory-Aligned Structures** with cache-optimized data layouts
- **Real-Time Systems** with deterministic timing guarantees

</td>
<td width="50%">

### AI & Machine Learning

- **Deep RL**: TD3, DDPG with Prioritized Experience Replay
- **Detection**: RF-DETR, DETR, YOLOv8 with TensorRT acceleration
- **Tracking**: Extended Kalman Filters, Mahalanobis gating
- **Optimization**: ONNX, TensorRT, FP16/INT8 quantization
- **Edge AI**: Raspberry Pi deployment, embedded inference

</td>
</tr>
</table>

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" width="100%">

## Featured Projects

<br/>

<!-- Project 1: Helix Drone -->
<div align="center">
<img src="https://img.shields.io/badge/HELIX_DRONE-Research_Grade_Quadrotor_Simulation-1a1a2e?style=for-the-badge&labelColor=0d1117"/>
</div>

<br/>

<table>
<tr>
<td align="center" width="120">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg" width="48" height="48" alt="C++"/>
<br><strong>C++17</strong>
</td>
<td align="center" width="120">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="48" height="48" alt="Python"/>
<br><strong>Python</strong>
</td>
<td align="center" width="120">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pytorch/pytorch-original.svg" width="48" height="48" alt="PyTorch"/>
<br><strong>PyTorch</strong>
</td>
<td align="center" width="120">
<img src="https://skillicons.dev/icons?i=cmake" width="48" height="48" alt="CMake"/>
<br><strong>CMake</strong>
</td>
</tr>
</table>

A research-grade quadrotor simulation platform engineered for training autonomous flight controllers via deep reinforcement learning. The architecture couples a **high-performance C++ physics core** with a **modular Python training pipeline**.

<details>
<summary><b>Physics Engine Architecture (C++)</b></summary>
<br/>

| Module | Implementation |
|:-------|:---------------|
| **Rigid Body Dynamics** | Full 6-DOF Newton-Euler equations with quaternion normalization |
| **Numerical Integration** | RK4, RK45 adaptive step-size, Velocity Verlet with sub-stepping |
| **Rotor Aerodynamics** | Blade Element Theory coupled with momentum theory |
| **Ground Effect** | Height-dependent thrust augmentation model |
| **Motor Dynamics** | First-order lag with ESC response, thermal derating curves |
| **Battery Model** | State-of-charge curves, internal resistance, voltage sag |
| **Wind Turbulence** | MIL-SPEC Dryden model with configurable intensity scales |

```cpp
class alignas(64) Quadrotor {
    void stepWithSubStepping(const MotorCommand& command, double agentDt);
    void stepAdaptive(const MotorCommand& command, double& dt);
    
    Vec3 computeTotalThrust() const noexcept;
    Vec3 computeAerodynamicForces(const Vec3& velocityBody) const noexcept;
    Vec3 computeGyroscopicTorque() const noexcept;
    Mat3 computeInertiaInverse() const noexcept;
};
```

</details>

<details>
<summary><b>Training Pipeline Architecture (Python)</b></summary>
<br/>

| Component | Description |
|:----------|:------------|
| **TD3 Agent** | Twin Delayed DDPG with target policy smoothing and delayed updates |
| **Experience Replay** | Sum-tree based prioritized sampling with importance weighting |
| **Environment** | Gymnasium-compliant with configurable task modes |
| **Domain Randomization** | Stochastic variation of mass, inertia, motor constants |
| **Curriculum Learning** | Progressive difficulty scaling for stable policy convergence |
| **Vectorization** | Parallel environment execution via SubprocVecEnv |

```python
class TD3Agent:
    def select_action(self, state: np.ndarray, exploration: bool = True) -> np.ndarray:
        with torch.no_grad():
            action = self.actor(state)
            if exploration:
                action += self.exploration_noise.sample()
        return action.clamp(-1.0, 1.0).cpu().numpy()
```

</details>

<br/>

<!-- Section Divider -->
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" width="100%">

<!-- Project 2: GeoGauge -->
<div align="center">
<img src="https://img.shields.io/badge/GEOGAUGE-AI_Road_Damage_Assessment-1a1a2e?style=for-the-badge&labelColor=0d1117"/>
</div>

<br/>

<table>
<tr>
<td align="center" width="120">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="48" height="48" alt="Python"/>
<br><strong>Python</strong>
</td>
<td align="center" width="120">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pytorch/pytorch-original.svg" width="48" height="48" alt="PyTorch"/>
<br><strong>PyTorch</strong>
</td>
<td align="center" width="120">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/opencv/opencv-original.svg" width="48" height="48" alt="OpenCV"/>
<br><strong>OpenCV</strong>
</td>
<td align="center" width="120">
<img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" width="100" height="32" alt="Streamlit"/>
<br><strong>Streamlit</strong>
</td>
</tr>
</table>

An end-to-end pipeline for automated pothole detection, metric depth estimation, and severity classification from monocular imagery. Designed for municipal infrastructure assessment with priority-based maintenance scheduling.

<details>
<summary><b>Detection and Depth Pipeline</b></summary>
<br/>

| Stage | Technology |
|:------|:-----------|
| **Object Detection** | YOLOv8 fine-tuned for multi-class road damage |
| **Depth Estimation** | Depth Anything v2 for dense monocular depth |
| **Plane Fitting** | RANSAC-based ground plane estimation |
| **Depth Refinement** | Guided filtering for edge-preserving smoothing |
| **Metric Calibration** | Camera intrinsics for physical measurements |

```python
class PotholeAnalyzer:
    def analyze_image(self, image_np_bgr: np.ndarray) -> List[Dict]:
        detections = self._detect_potholes(image_rgb)
        depth_map = self._get_depth_map(image_rgb)
        ground_plane = self._fit_ground_plane(depth_map)
        return self._compute_severity_metrics(detections, depth_map, ground_plane)
```

</details>

<details>
<summary><b>Severity Classification System</b></summary>
<br/>

| Feature | Method |
|:--------|:-------|
| **Dimensional Analysis** | Metric extraction of length, width, depth |
| **Confidence Mapping** | Detection probability weighting |
| **Multi-Factor Scoring** | Geometric + contextual features fusion |
| **Priority Ranking** | Automated maintenance queue generation |

</details>

<br/>

<!-- Section Divider -->
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" width="100%">

<!-- Project 3: LiveCam AI -->
<div align="center">
<img src="https://img.shields.io/badge/LIVECAM_AI-Real_Time_Ball_Tracking-1a1a2e?style=for-the-badge&labelColor=0d1117"/>
</div>

<br/>

<table>
<tr>
<td align="center" width="120">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="48" height="48" alt="Python"/>
<br><strong>Python</strong>
</td>
<td align="center" width="120">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pytorch/pytorch-original.svg" width="48" height="48" alt="PyTorch"/>
<br><strong>PyTorch</strong>
</td>
<td align="center" width="120">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/opencv/opencv-original.svg" width="48" height="48" alt="OpenCV"/>
<br><strong>OpenCV</strong>
</td>
<td align="center" width="120">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/numpy/numpy-original.svg" width="48" height="48" alt="NumPy"/>
<br><strong>NumPy</strong>
</td>
</tr>
</table>

A low-latency ball tracking system for sports analytics combining **Transformer-based detection** with **probabilistic state estimation** for robust tracking under occlusion, motion blur, and rapid direction changes.

<details>
<summary><b>Detection Architecture</b></summary>
<br/>

| Component | Implementation |
|:----------|:---------------|
| **Backbone** | RF-DETR (Region-Focused Detection Transformer) |
| **Multi-Scale** | Adaptive resolution for varying object sizes |
| **Precision** | FP16 inference with TensorRT optimization |
| **Temporal Fusion** | Detection history for confidence smoothing |
| **ROI Processing** | Dynamic region-of-interest for computational efficiency |

</details>

<details>
<summary><b>Tracking Architecture</b></summary>
<br/>

| Component | Implementation |
|:----------|:---------------|
| **State Estimator** | Extended Kalman Filter with 6-state model |
| **Gating** | Mahalanobis distance for statistical outlier rejection |
| **Noise Adaptation** | Dynamic process/measurement noise tuning |
| **Smoothing** | One-Euro Filter with adaptive cutoff frequency |
| **Hypothesis Management** | Multi-hypothesis tracking for ambiguity resolution |

```python
class ExtendedKalmanFilter:
    def predict(self, dt: float) -> np.ndarray:
        self._update_transition_matrix(dt)
        self.x = self.F @ self.x
        self.P = self.F @ self.P @ self.F.T + self.Q
        return self.x[:2]

    def update(self, z: np.ndarray, confidence: float) -> np.ndarray:
        d = mahalanobis_distance(z, self.x[:2], self.P[:2, :2])
        if d < self.gate_threshold:
            self._kalman_update(z, confidence)
        return self.x[:2]
```

</details>

<br/>

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" width="100%">

## Technical Expertise

<div align="center">

<br/>

<!-- Animated Technology Categories -->
<table>
<tr>
<td align="center" width="50%">

### Languages & Core

<br/>

![C++](https://img.shields.io/badge/C++-17/20-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)
![CUDA](https://img.shields.io/badge/CUDA-12.x-76B900?style=flat-square&logo=nvidia&logoColor=white)
![CMake](https://img.shields.io/badge/CMake-064F8C?style=flat-square&logo=cmake&logoColor=white)

</td>
<td align="center" width="50%">

### Machine Learning

<br/>

![PyTorch](https://img.shields.io/badge/PyTorch-2.x-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![TensorRT](https://img.shields.io/badge/TensorRT-76B900?style=flat-square&logo=nvidia&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=flat-square&logo=onnx&logoColor=white)
![Gymnasium](https://img.shields.io/badge/Gymnasium-0081A5?style=flat-square)

</td>
</tr>
<tr>
<td align="center" width="50%">

### Computer Vision

<br/>

![OpenCV](https://img.shields.io/badge/OpenCV-4.x-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![Ultralytics](https://img.shields.io/badge/Ultralytics-00FFFF?style=flat-square)
![Supervision](https://img.shields.io/badge/Roboflow-8338EC?style=flat-square)

</td>
<td align="center" width="50%">

### Infrastructure

<br/>

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![RaspberryPi](https://img.shields.io/badge/RPi-A22846?style=flat-square&logo=raspberrypi&logoColor=white)

</td>
</tr>
</table>

</div>

<br/>

<!-- Domain Expertise Matrix -->
<div align="center">

| Domain | Technologies | Applications |
|:------:|:-------------|:-------------|
| **Physics Simulation** | C++17, SIMD, RK4/RK45, Quaternions | Quadrotor dynamics, rigid body mechanics |
| **Reinforcement Learning** | TD3, DDPG, PER, Curriculum Learning | Autonomous control, policy optimization |
| **Object Detection** | RF-DETR, YOLOv8, DETR, Vision Transformers | Sports analytics, infrastructure inspection |
| **State Estimation** | EKF, Mahalanobis Gating, One-Euro Filter | Multi-object tracking, sensor fusion |
| **Depth Estimation** | Monocular depth, RANSAC, Guided Filtering | 3D reconstruction, metric measurement |
| **Edge Deployment** | TensorRT, ONNX, FP16/INT8, Raspberry Pi | Real-time inference, embedded AI |

</div>

<br/>

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" width="100%">

## Analytics

<div align="center">

<br/>

<!-- GitHub Stats Grid - Using stable anuraghazra vercel instance -->
<a href="https://github.com/chele-s">
  <img src="https://github-readme-stats-sigma-five.vercel.app/api?username=chele-s&show_icons=true&theme=dark&hide_border=true&include_all_commits=true&count_private=true&bg_color=0d1117&title_color=58a6ff&icon_color=1f6feb&text_color=c9d1d9" height="180" alt="GitHub Stats"/>
</a>
<a href="https://github.com/chele-s">
  <img src="https://github-readme-stats-sigma-five.vercel.app/api/top-langs/?username=chele-s&layout=compact&theme=dark&hide_border=true&langs_count=8&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9" height="180" alt="Top Languages"/>
</a>

<br/><br/>

<!-- Streak Stats - Using streak-stats.demolab.com which is more reliable -->
<a href="https://github.com/chele-s">
  <img src="https://streak-stats.demolab.com?user=chele-s&theme=dark&hide_border=true&background=0d1117&stroke=30363d&ring=58a6ff&fire=58a6ff&currStreakLabel=58a6ff&sideLabels=c9d1d9&dates=8b949e" alt="GitHub Streak"/>
</a>

<br/><br/>

<!-- Trophy Collection - Using algolia theme which is always available -->
<a href="https://github.com/chele-s">
  <img src="https://github-profile-trophy.vercel.app/?username=chele-s&theme=algolia&no-frame=true&no-bg=true&row=1&column=7&margin-w=15" alt="Trophies"/>
</a>

<br/><br/>

<!-- Activity Graph -->
<a href="https://github.com/chele-s">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=chele-s&theme=github-compact&hide_border=true&bg_color=0d1117&color=58a6ff&line=1f6feb&point=58a6ff&area=true&area_color=1f6feb" width="95%" alt="Activity Graph"/>
</a>

</div>

<br/>

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" width="100%">

## Contribution Graph

<div align="center">

<!-- 3D Contribution Calendar - No GitHub Actions required -->
<a href="https://github.com/chele-s">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=chele-s&theme=github_dark" width="95%" alt="Contribution Graph"/>
</a>

<br/>

<a href="https://github.com/chele-s">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=chele-s&theme=github_dark&utcOffset=-6" width="45%" alt="Productive Time"/>
</a>
<a href="https://github.com/chele-s">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=chele-s&theme=github_dark" width="45%" alt="Repos per Language"/>
</a>

</div>

<br/>

<!-- Animated Footer -->
<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:1a1a2e,100:16213e&height=120&section=footer"/>

<div align="center">

<br/>

**Building intelligent systems that bridge physical reality and computational intelligence.**

<br/>

![Visitor Count](https://komarev.com/ghpvc/?username=chele-s&style=for-the-badge&color=1f6feb&label=Profile+Views)

<br/>

<sub><b>El Salvador</b> • Systems Engineer • Open to Collaboration</sub>

</div>
