# Awesome FOSS for Decentralised Manufacturing [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of Free and Open Source Software (FOSS) tools, firmware, open hardware designs, file formats, and resources that form the structural backbone of decentralised digital fabrication ecosystems.

This list is companion material to the paper:

> **Dogančić, B., Rožić, J., Jokić, M., & Čeredar, M. (2026).** *Decentralised Manufacturing as a Networked Cyber-Physical System: Formalising Free and Open Source Software Governance and ML Adaptation for Distributed Robustness.* Systems, 2026. \[waiting for publishing\]

The paper proposes a systems-theoretic framework that models decentralised manufacturing as a networked cyber-physical system (CPS). FOSS ecosystems are formalised as the **structural governance layer** — the *Design Rules* (Baldwin & Clark, 2000) — that enables heterogeneous, autonomously operated fabrication nodes to remain interoperable without centralised control. At each node, a **Cognitive Gateway** (a co-located software layer combining a digital twin nominal model, an ML disturbance estimator, and an Admission Controller) automates what an experienced human operator does manually: compensating for process drift, filtering incoming calibration updates from the network, and propagating learned corrections via federated learning to structurally similar nodes. The framework is applied analytically to three disturbance classes — regulatory restriction, technical process variability, and supply-chain disruption — and demonstrates that FOSS-governed decentralisation provides structural robustness through redundancy, component substitutability, and informational persistence that centralised architectures cannot replicate.

Every tool listed below is a concrete instance of that governance architecture: a substitutable, transparent, community-maintained component that keeps the distributed fabrication stack interoperable and resilient.

**Why does this matter?** As fabrication capability moves from centralised factories to distributed workshops, homes, and makerspaces, the resilience of the entire ecosystem depends on open interfaces and substitutable components. Proprietary lock-in at any layer — design, toolpath generation, firmware, or material supply — introduces single points of failure that compound under regulatory pressure, supply-chain disruption, and process variability. This list maps the FOSS landscape that prevents such fragmentation.

---

## Contents

- [CAD — Computer-Aided Design](#cad--computer-aided-design)
  - [Parametric & Solid Modelling](#parametric--solid-modelling)
  - [Mesh & Direct Modelling](#mesh--direct-modelling)
  - [Programmatic & Script-Based CAD](#programmatic--script-based-cad)
  - [2D Vector Design](#2d-vector-design)
  - [PCB & Electronics Design](#pcb--electronics-design)
- [CAM — Computer-Aided Manufacturing](#cam--computer-aided-manufacturing)
  - [Slicer Software (Additive Manufacturing)](#slicer-software-additive-manufacturing)
  - [Nesting / Sheet Layout](#nesting)
  - [CNC Toolpath Generation (Subtractive)](#cnc-toolpath-generation-subtractive)
  - [Laser / Plasma Toolpath](#laser--plasma-toolpath)
- [Machine Control Firmware](#machine-control-firmware)
  - [3D Printer Firmware](#3d-printer-firmware)
  - [CNC & Motion Control Firmware](#cnc--motion-control-firmware)
  - [Laser Cutter Firmware](#laser-cutter-firmware)
- [Machine Control Interfaces & Hosts](#machine-control-interfaces--hosts)
- [CAE — Simulation & Analysis](#cae--simulation--analysis)
  - [Finite Element Analysis (FEA)](#finite-element-analysis-fea)
  - [Computational Fluid Dynamics (CFD)](#computational-fluid-dynamics-cfd)
  - [Multi-Physics & General Solvers](#multi-physics--general-solvers)
  - [Pre/Post Processing & Meshing](#prepost-processing--meshing)
- [File Formats & Interchange Standards](#file-formats--interchange-standards)
- [Process Monitoring & Digital Twins](#process-monitoring--digital-twins)
- [Machine Learning for Manufacturing](#machine-learning-for-manufacturing)
  - [ML Frameworks](#ml-frameworks)
  - [Federated Learning](#federated-learning)
  - [Computer Vision & Defect Detection](#computer-vision--defect-detection)
  - [Bayesian Optimisation & Gaussian Processes](#bayesian-optimisation--gaussian-processes)
- [Open Hardware Designs](#open-hardware-designs)
  - [3D Printers (FDM/FFF)](#3d-printers-fdmfff)
  - [Resin Printers (SLA/DLP/MSLA)](#resin-printers-sladlpmsla)
  - [CNC Machines & Routers](#cnc-machines--routers)
  - [Laser Cutters & Engravers](#laser-cutters--engravers)
  - [Other Fabrication Hardware](#other-fabrication-hardware)
  - [Control Electronics](#control-electronics)
- [Design Repositories & Commons](#design-repositories--commons)
- [Community & Knowledge Sharing](#community--knowledge-sharing)
- [Supply Chain & Material Databases](#supply-chain--material-databases)
- [Related Awesome Lists](#related-awesome-lists)
- [Contributing](#contributing)
- [License](#license)

---

## CAD — Computer-Aided Design

### Parametric & Solid Modelling

| Project | Description | License |
|---------|-------------|---------|
| [FreeCAD](https://github.com/FreeCAD/FreeCAD) | Full-featured parametric 3D modeller with Part, PartDesign, Assembly, FEM, Path (CAM), and BIM workbenches. The most complete FOSS CAD package. | LGPL-2.1 |
| [SolveSpace](https://github.com/solvespace/solvespace) | Lightweight parametric 2D/3D constraint-based CAD. Excellent for mechanical sketching with a small footprint. | GPL-3.0 |
| [CadQuery](https://github.com/CadQuery/cadquery) | Python-based parametric CAD scripting library built on the OCCT kernel. Integrates well with Jupyter notebooks. | Apache-2.0 |
| [Build123d](https://github.com/gumyr/build123d) | Next-generation Python CAD API built on CadQuery/OCCT with a more pythonic, builder-pattern interface. | Apache-2.0 |
| [BRL-CAD](https://github.com/BRL-CAD/brlcad) | Constructive Solid Geometry (CSG) modeller maintained by the U.S. Army Research Laboratory. One of the oldest FOSS CAD systems. | LGPL-2.1 |

### Mesh & Direct Modelling

| Project | Description | License |
|---------|-------------|---------|
| [Blender](https://github.com/blender/blender) | Full 3D creation suite — modelling, sculpting, animation, rendering. Increasingly used for engineering visualisation and 3D print preparation. | GPL-2.0+ |
| [MeshLab](https://github.com/cnr-isti-vclab/meshlab) | Mesh processing and editing. Useful for STL repair, decimation, and scan cleanup. | GPL-3.0 |
| [Meshmixer](https://meshmixer.com/) | Mesh editing and repair tool (free but not open source — included for ecosystem completeness). | Proprietary (free) |

### Programmatic & Script-Based CAD

| Project | Description | License |
|---------|-------------|---------|
| [OpenSCAD](https://github.com/openscad/openscad) | Script-based solid modelling using CSG. The de facto standard for parametric open-source hardware design. | GPL-2.0 |
| [ImplicitCAD](https://github.com/Haskell-Things/ImplicitCAD) | Haskell-based programmatic CAD with implicit surface representation. | AGPL-3.0 |
| [JSCAD (OpenJSCAD)](https://github.com/jscad/OpenJSCAD.org) | JavaScript-based solid modelling, runs in the browser. | MIT |
| [libfive](https://github.com/libfive/libfive) | Solid modelling kernel using f-rep (functional representation) — fast, GPU-accelerated. | (M/L)GPL |

### 2D Vector Design

| Project | Description | License |
|---------|-------------|---------|
| [Inkscape](https://github.com/inkscape/inkscape) | Professional vector graphics editor. Widely used for laser cutting and vinyl cutting toolpath preparation. | GPL-2.0 |
| [LibreCAD](https://github.com/LibreCAD/LibreCAD) | 2D CAD application for technical drawings. DXF-native. | GPL-2.0 |

### PCB & Electronics Design

| Project | Description | License |
|---------|-------------|---------|
| [KiCad](https://github.com/KiCad/kicad-source-mirror) | Full-featured schematic capture and PCB layout. Industry-grade, backed by CERN. Essential for designing custom control electronics. | GPL-3.0 |
| [Horizon EDA](https://github.com/horizon-eda/horizon) | Modern EDA for PCB design with focus on good library management. | GPL-3.0 |

---

## CAM — Computer-Aided Manufacturing

### Slicer Software (Additive Manufacturing)

| Project | Description | License |
|---------|-------------|---------|
| [PrusaSlicer](https://github.com/prusa3d/PrusaSlicer) | Feature-rich FDM/SLA slicer. Fork of Slic3r with active development. Supports wide range of printers via community profiles. | AGPL-3.0 |
| [Cura](https://github.com/Ultimaker/Cura) | Popular FDM slicer with extensive plugin ecosystem and community machine profiles. | LGPL-3.0 |
| [SuperSlicer](https://github.com/supermerill/SuperSlicer) | Fork of PrusaSlicer with additional calibration and tuning features for power users. | AGPL-3.0 |
| [OrcaSlicer](https://github.com/SoftFever/OrcaSlicer) | Fork of PrusaSlicer/BambuStudio with multicolour, multi-material, and Klipper-oriented features. | AGPL-3.0 |
| [Slic3r](https://github.com/slic3r/Slic3r) | The original open-source slicer that spawned PrusaSlicer, SuperSlicer, and OrcaSlicer. Foundational to the ecosystem. | AGPL-3.0 |
| [CuraEngine](https://github.com/Ultimaker/CuraEngine) | The slicing engine behind Cura. Can be used standalone or embedded in other applications. | AGPL-3.0 |
| [Chitubox Basic](https://www.chitubox.com/) | Resin (SLA/DLP/MSLA) slicer (free but not open source — included for ecosystem completeness). | Proprietary (free) |
| [UVtools](https://github.com/sn4k3/UVtools) | MSLA/DLP file editor and analyser. Supports many resin printer file formats. | AGPL-3.0 |

### Nesting
| Project | Description | License |
|---------|-------------|---------|
| [Kenzap Nesting](https://github.com/kenzap/nesting-app) | Desktop 2D nesting tool that arranges DXF parts on sheets and exports the layouts as DXF. Runs on macOS, Windows, and Linux. | Apache-2.0 |

### CNC Toolpath Generation (Subtractive)

| Project | Description | License |
|---------|-------------|---------|
| [FreeCAD Path Workbench](https://github.com/FreeCAD/FreeCAD) | Integrated CAM within FreeCAD — generates G-code toolpaths from 3D models. | LGPL-2.1 |
| [CAMotics](https://github.com/CamoticS/camotics) | Open-source CNC simulation and G-code visualisation. Useful for toolpath verification before cutting. | GPL-2.0+ |
| [dxf2gcode](https://github.com/luzpaz/dxf2gcode) | Converts DXF drawings to G-code for CNC milling and engraving. | GPL-3.0 |
| [jscut](https://github.com/nicholasgasior/jscut) | Browser-based CNC CAM from SVG files. Generates G-code for 2.5D milling. | GPL-3.0 |
| [PyCAM](https://github.com/SebKuwormo/pycam) | 3-axis toolpath generator for CNC machining. | GPL-3.0 |
| [bCNC](https://github.com/vlachoudis/bCNC) | G-code sender and CNC controller with CAM capabilities, probe support, and autolevel. | GPL-2.0 |

### Laser / Plasma Toolpath

| Project | Description | License |
|---------|-------------|---------|
| [LightBurn](https://lightburnsoftware.com/) | Widely used laser cutter software (proprietary — included for ecosystem context; FOSS alternatives below serve the same role). | Proprietary |
| [LaserWeb](https://github.com/LaserWeb/LaserWeb4) | Open-source laser cutter / CNC controller with browser-based interface. Supports Grbl, Smoothieware, Marlin. | GPL-3.0 |
| [VisiCut](https://github.com/t-oster/VisiCut) | Laser cutter toolpath preparation, especially popular in FabLabs and makerspaces. | LGPL-3.0 |
| [K40 Whisperer](https://github.com/jkramarz/K40-Whisperer) | Control software for the ubiquitous K40 CO₂ laser cutters. | GPL-3.0 |
| [MeerK40t](https://github.com/meerk40t/meerk40t) | Modern Python-based controller for K40 and other laser cutters. | MIT |

---

## Machine Control Firmware

### 3D Printer Firmware

| Project | Description | License |
|---------|-------------|---------|
| [Marlin](https://github.com/MarlinFirmware/Marlin) | The most widely used open-source 3D printer firmware. Runs on 8-bit and 32-bit boards. Mature, extensive hardware support. | GPL-3.0 |
| [Klipper](https://github.com/Klipper3d/klipper) | High-performance firmware using a host computer (Raspberry Pi) for computation and microcontroller for real-time stepping. Enables input shaping, pressure advance, and advanced kinematics. | GPL-3.0 |
| [RepRapFirmware](https://github.com/Duet3D/RepRapFirmware) | Feature-rich firmware for Duet boards. Supports advanced kinematics, network control, and CNC/laser modes. | GPL-3.0 |
| [Smoothieware](https://github.com/Smoothieware/Smoothieware) | Firmware for Smoothieboard and LPC-based controllers. Supports 3D printing, CNC, and laser cutting. | GPL-3.0 |
| [teacup](https://github.com/Traumflug/Teacup_Firmware) | Minimalist RepRap firmware with a small footprint for constrained microcontrollers. | GPL-2.0 |

### CNC & Motion Control Firmware

| Project | Description | License |
|---------|-------------|---------|
| [LinuxCNC](https://github.com/LinuxCNC/linuxcnc) | Industrial-grade CNC controller running on real-time Linux. Supports milling, turning, plasma, laser, and robotics. | GPL-2.0 |
| [Grbl](https://github.com/grbl/grbl) | High-performance G-code interpreter and CNC motion controller for Arduino (ATmega328p). The foundation for many CNC and laser builds. | GPL-3.0 |
| [grblHAL](https://github.com/grblHAL) | Modern 32-bit port of Grbl supporting multiple MCU platforms (STM32, ESP32, RP2040, iMXRT, SAM). | GPL-3.0 |
| [FluidNC](https://github.com/bdring/FluidNC) | ESP32-based CNC controller firmware. Wi-Fi enabled, highly configurable via YAML. Successor to Grbl_ESP32. | GPL-3.0 |
| [TinyG](https://github.com/synthetos/TinyG) | 6-axis CNC motion control with advanced jerk-controlled motion planning. | GPL-2.0 |
| [g2core](https://github.com/synthetos/g2) | ARM-based successor to TinyG with enhanced motion control. | GPL-2.0 |

### Laser Cutter Firmware

| Project | Description | License |
|---------|-------------|---------|
| [Grbl](https://github.com/grbl/grbl) / [grblHAL](https://github.com/grblHAL) | Most DIY and semi-professional laser cutters use Grbl-based firmware for motion control. | GPL-3.0 |
| [Smoothieware](https://github.com/Smoothieware/Smoothieware) | Native laser mode with PWM power control. | GPL-3.0 |
| [K40 firmware variants](https://github.com/meerk40t/meerk40t) | Community firmware replacements for K40 laser cutter stock boards. | Various |

---

## Machine Control Interfaces & Hosts

| Project | Description | License |
|---------|-------------|---------|
| [OctoPrint](https://github.com/OctoPrint/OctoPrint) | Web-based 3D printer host and control interface. Extensive plugin ecosystem for monitoring, timelapse, and remote control. | AGPL-3.0 |
| [Mainsail](https://github.com/mainsail-crew/mainsail) | Modern web interface for Klipper firmware. Lightweight, responsive. | GPL-3.0 |
| [Fluidd](https://github.com/fluidd-core/fluidd) | Alternative web interface for Klipper with a clean, intuitive UI. | GPL-3.0 |
| [Moonraker](https://github.com/Arksine/moonraker) | API web server for Klipper. Provides the REST/WebSocket API that Mainsail and Fluidd use. | GPL-3.0 |
| [Pronterface / Printrun](https://github.com/kliment/Printrun) | Classic desktop host software for G-code sending and printer control. | GPL-3.0 |
| [Repetier-Host](https://www.repetier.com/) | Desktop host for 3D printer control (partially open source). | Mixed |
| [CNCjs](https://github.com/cncjs/cncjs) | Web-based CNC controller interface. Supports Grbl, Smoothieware, TinyG, and others. | MIT |
| [Universal G-code Sender (UGS)](https://github.com/winder/Universal-G-Code-Sender) | Java-based G-code sender for CNC machines. Cross-platform. | GPL-3.0 |
| [Candle](https://github.com/Denvi/Candle) | GUI for Grbl-based CNC machines with 3D visualisation of toolpaths. | GPL-3.0 |
| [Duet Web Control](https://github.com/Duet3D/DuetWebControl) | Web interface for RepRapFirmware/Duet boards. | GPL-3.0 |

---

## CAE — Simulation & Analysis

### Finite Element Analysis (FEA)

| Project | Description | License |
|---------|-------------|---------|
| [CalculiX](http://www.dhondt.de/) | 3D structural FEA solver (CCX) and pre/post-processor (CGX). Abaqus-compatible input format. | GPL-2.0 |
| [Code_Aster / code_aster](https://code-aster.org/) | Advanced thermo-mechanical FEA solver developed by EDF. Covers structural, thermal, and fatigue analysis. | GPL |
| [FreeCAD FEM Workbench](https://github.com/FreeCAD/FreeCAD) | Integrated FEA environment within FreeCAD using CalculiX, Elmer, or Z88 as backend solvers. | LGPL-2.1 |
| [Elmer](https://github.com/ElmerCSC/elmerfem) | Multi-physics FEA solver covering structural, thermal, electromagnetics, fluid, and acoustics. | GPL-2.0 |
| [Z88Aurora](https://en.z88.de/) | Lightweight FEA package with a graphical interface for static analysis. | Free (binaries) |
| [MOOSE](https://github.com/idaholab/moose) | Multi-physics Object-Oriented Simulation Environment by Idaho National Lab. Framework for building custom FEA solvers. | LGPL-2.1 |
| [deal.II](https://github.com/dealii/dealii) | Adaptive finite element library (C++) for solving PDEs. | LGPL-2.1 |
| [FEniCS / FEniCSx](https://github.com/FEniCS) | High-level Python/C++ platform for solving PDEs with the finite element method. | LGPL-3.0 |
| [GetDP](https://getdp.info/) | General environment for the treatment of discrete problems — particularly strong in electromagnetics. | GPL-2.0 |

### Computational Fluid Dynamics (CFD)

| Project | Description | License |
|---------|-------------|---------|
| [OpenFOAM](https://github.com/OpenFOAM) | Industry-standard FOSS CFD toolbox. Extensive range of solvers for incompressible/compressible flows, combustion, heat transfer. | GPL-3.0 |
| [SU2](https://github.com/su2code/SU2) | CFD suite particularly suited for aerodynamic shape optimisation. | LGPL-2.1 |
| [Palabos](https://palabos.unige.ch/) | Lattice Boltzmann CFD solver for complex fluid dynamics. | AGPL-3.0 |

### Multi-Physics & General Solvers

| Project | Description | License |
|---------|-------------|---------|
| [Kratos Multiphysics](https://github.com/KratosMultiphysics/Kratos) | Framework for building parallel multi-physics simulation environments. | BSD-3 |
| [Gmsh](https://gmsh.info/) | 3D finite element mesh generator with CAD engine and post-processor. Works as a front-end for many solvers. | GPL-2.0+ |
| [Salome-Meca](https://www.code-aster.org/spip.php?rubrique2) | Integration platform combining geometry, meshing (Salome), and FEA solving (Code_Aster). | LGPL |

### Pre/Post Processing & Meshing

| Project | Description | License |
|---------|-------------|---------|
| [Gmsh](https://gmsh.info/) | Mesh generation with built-in CAD engine. Tetrahedral, hexahedral, and mixed meshes. | GPL-2.0+ |
| [Salome](https://www.salome-platform.org/) | Pre/post-processing platform for numerical simulation — geometry, meshing, visualisation. | LGPL-2.1 |
| [ParaView](https://github.com/Kitware/ParaView) | Data analysis and visualisation platform for large datasets. Standard post-processor for FEA/CFD results. | BSD-3 |
| [Netgen / NGSolve](https://github.com/NGSolve/netgen) | Automatic mesh generator and high-order finite element solver. | LGPL-2.1 |
| [enGrid](https://github.com/enGits/engrid) | Mesh generation for CFD (especially OpenFOAM compatibility). | GPL-3.0 |
| [cfMesh](https://cfmesh.com/) | Automatic mesh generator for OpenFOAM. | GPL-3.0 |

---

## File Formats & Interchange Standards

Open, standardised file formats are the **interface boundaries** that enable interoperability across the FOSS fabrication stack. Without them, no amount of open-source tooling achieves substitutability.

| Format | Domain | Description |
|--------|--------|-------------|
| **STL** | Geometry exchange | Triangulated surface mesh. Universal 3D printing interchange format. Simple but lossy (no colour, units, or metadata). |
| **3MF** | Geometry + metadata | Modern replacement for STL. Supports colour, materials, units, build layout, and is backed by an open consortium. |
| **STEP (AP203/AP214)** | CAD interchange | ISO 10303 standard for exchanging solid models between CAD systems. Preserves parametric topology. |
| **IGES** | CAD interchange (legacy) | Older geometry exchange format. Still used for interop with legacy systems. |
| **G-code (RS-274)** | Machine control | De facto standard for CNC and 3D printer toolpath instructions. Text-based, human-readable. |
| **DXF** | 2D drawing | AutoCAD Drawing Exchange Format. Widely used for laser cutting and 2D CNC profiles. |
| **SVG** | 2D vector | W3C standard vector format. Used for laser cutting and vinyl cutting via Inkscape and other tools. |
| **OBJ** | Mesh/geometry | Wavefront geometry format. Simple, widely supported for mesh exchange. |
| **AMF** | Additive manufacturing | ISO/ASTM 52915 standard for AM data. Supports curved triangles, colour, materials, and constellations. |
| **BREP** | Solid geometry | Boundary representation format used internally by OpenCASCADE (FreeCAD, CadQuery). |
| **PLY** | Point cloud / mesh | Stanford Triangle Format. Common for 3D scanning output. |
| **glTF / GLB** | 3D visualisation | Khronos standard for efficient 3D model transmission. Increasingly used for digital twin visualisation. |

---

## Process Monitoring & Digital Twins

| Project | Description | License |
|---------|-------------|---------|
| [OctoPrint](https://github.com/OctoPrint/OctoPrint) | 3D printer monitoring with webcam, thermal tracking, and extensive plugin ecosystem (also listed under host software). | AGPL-3.0 |
| [Obico (formerly The Spaghetti Detective)](https://github.com/TheSpaghettiDetective/obico-server) | AI-powered print failure detection. Self-hostable server with ML-based monitoring. | AGPL-3.0 |
| [Eclipse Ditto](https://github.com/eclipse-ditto/ditto) | Framework for digital twin representation and management of IoT devices. | EPL-2.0 |
| [Eclipse Hono](https://github.com/eclipse-hono/hono) | IoT messaging infrastructure for connecting devices at scale — can serve as telemetry backbone for distributed fabrication nodes. | EPL-2.0 |
| [Grafana](https://github.com/grafana/grafana) | Dashboarding and observability platform. Widely used for monitoring CNC machines and 3D printers via time-series data. | AGPL-3.0 |
| [InfluxDB](https://github.com/influxdata/influxdb) | Time-series database commonly paired with Grafana for machine telemetry storage. | MIT / Apache-2.0 |
| [Prometheus](https://github.com/prometheus/prometheus) | Monitoring and alerting toolkit with a time-series database. Pull-based metrics collection. | Apache-2.0 |
| [Node-RED](https://github.com/node-red/node-red) | Flow-based programming for IoT. Useful for wiring together sensors, machine APIs, and dashboards. | Apache-2.0 |
| [Moonraker](https://github.com/Arksine/moonraker) | Exposes Klipper printer state as a REST API — a building block for custom digital twin implementations. | GPL-3.0 |

---

## Machine Learning for Manufacturing

### ML Frameworks

| Project | Description | License |
|---------|-------------|---------|
| [PyTorch](https://github.com/pytorch/pytorch) | Deep learning framework. Widely used for defect detection, process prediction, and generative design. | BSD-3 |
| [TensorFlow](https://github.com/tensorflow/tensorflow) | ML platform with broad deployment options (edge, mobile, server). | Apache-2.0 |
| [scikit-learn](https://github.com/scikit-learn/scikit-learn) | Classical ML library (Python). Regression, classification, clustering for process parameter optimisation. | BSD-3 |
| [JAX](https://github.com/jax-ml/jax) | High-performance numerical computing with autodiff. Suitable for physics-informed ML. | Apache-2.0 |
| [ONNX Runtime](https://github.com/microsoft/onnxruntime) | Cross-platform inference engine. Enables deploying trained models to edge devices at fabrication nodes. | MIT |

### Federated Learning

| Project | Description | License |
|---------|-------------|---------|
| [Flower (flwr)](https://github.com/adap/flower) | Framework-agnostic federated learning. Supports PyTorch, TensorFlow, JAX, and custom ML backends. | Apache-2.0 |
| [PySyft](https://github.com/OpenMined/PySyft) | Privacy-preserving ML library supporting federated learning, differential privacy, and encrypted computation. | Apache-2.0 |
| [FATE](https://github.com/FederatedAI/FATE) | Industrial federated learning framework supporting various FL algorithms. | Apache-2.0 |
| [TensorFlow Federated](https://github.com/google-parfait/tensorflow-federated) | Federated learning and federated analytics framework built on TensorFlow. | Apache-2.0 |
| [FedML](https://github.com/FedML-AI/FedML) | Open research library for federated learning supporting diverse topologies and algorithms. | Apache-2.0 |
| [OpenFL](https://github.com/securefederatedai/openfl) | Intel's open federated learning framework. | Apache-2.0 |

### Computer Vision & Defect Detection

| Project | Description | License |
|---------|-------------|---------|
| [OpenCV](https://github.com/opencv/opencv) | Computer vision library. Foundation for in-situ print monitoring, dimensional inspection, and defect detection. | Apache-2.0 |
| [Ultralytics (YOLOv8/11)](https://github.com/ultralytics/ultralytics) | Real-time object detection. Applicable to print failure detection and quality inspection. | AGPL-3.0 |
| [Obico](https://github.com/TheSpaghettiDetective/obico-server) | ML-based 3D print failure detection (also listed under monitoring). | AGPL-3.0 |
| [Label Studio](https://github.com/HumanSignal/label-studio) | Data labelling platform for training custom defect detection models. | Apache-2.0 |

### Bayesian Optimisation & Gaussian Processes

| Project | Description | License |
|---------|-------------|---------|
| [GPyTorch](https://github.com/cornellius-gp/gpytorch) | Gaussian process library built on PyTorch. Scalable GP regression for process modelling. | MIT |
| [BoTorch](https://github.com/pytorch/botorch) | Bayesian optimisation library on GPyTorch. Suitable for process parameter optimisation. | MIT |
| [GPflow](https://github.com/GPflow/GPflow) | Gaussian process library using TensorFlow. | Apache-2.0 |
| [scikit-optimize](https://github.com/scikit-optimize/scikit-optimize) | Sequential model-based optimisation library built on scikit-learn. | BSD-3 |
| [Ax (Adaptive Experimentation)](https://github.com/facebook/Ax) | Platform for optimising experiments, including Bayesian optimisation. | MIT |

---

## Open Hardware Designs

### 3D Printers (FDM/FFF)

| Project | Description | License |
|---------|-------------|---------|
| [Voron Design](https://github.com/VoronDesign) | High-performance enclosed CoreXY printer family (V0, Trident, V2, Switchwire). Community-driven, BOM-sourced. | GPL-3.0 |
| [Prusa i3 MK-series](https://github.com/prusa3d) | Open-source printer designs from Prusa Research. The i3 design lineage is one of the most replicated in history. | GPL-3.0 |
| [RatRig V-Core](https://github.com/Rat-Rig) | CoreXY 3D printer with linear rail motion system and aluminium extrusion frame. | GPL-3.0 |
| [RepRap Project](https://reprap.org/) | The original self-replicating 3D printer project. Foundational to the entire open-source 3D printing ecosystem. | GPL |
| [Annex Engineering](https://github.com/Annex-Engineering) | Open-source printer and extruder designs (K3, Sherpa Mini, etc.). | GPL-3.0 |
| [HevORT](https://github.com/MirageC79/HevORT) | High-performance CoreXYZ printer designed for speed and rigidity. | GPL-3.0 |
| [Positron V3](https://github.com/KRALYN/PositronV3) | Upside-down, folding 3D printer design. Novel portable concept. | GPL-3.0 |
| [EVA (European Voron Alliance)](https://main.eva-3d.page/) | Universal carriage platform for various printer designs. | GPL-3.0 |

### Resin Printers (SLA/DLP/MSLA)

| Project | Description | License |
|---------|-------------|---------|
| [OpenExposer](https://github.com/mario-schallner/OpenExposer) | Open-source DLP 3D printer design. | GPL-3.0 |

### CNC Machines & Routers

| Project | Description | License |
|---------|-------------|---------|
| [PrintNC](https://wiki.printnc.info/) | Steel-frame CNC router designed to be built from common hardware store materials and 3D-printed parts. | Open Hardware |
| [MPCNC (Mostly Printed CNC)](https://www.v1e.com/) | Ryan Zellman's (V1 Engineering) CNC router made primarily from 3D-printed parts and conduit. | GPL-3.0 |
| [LowRider CNC](https://www.v1e.com/) | Large-format CNC router from V1 Engineering, designed for full-sheet cutting. | GPL-3.0 |
| [Root CNC](https://rootcnc.com/) | Open-source CNC machine designed for rigidity and accuracy. | Open Hardware |
| [Maslow CNC](https://github.com/MaslowCNC) | Vertical hanging CNC router for cutting full 4×8 sheets. | GPL-3.0 |
| [WorkBee CNC](https://ooznest.co.uk/workbee-cnc/) | V-slot based CNC router (open design, commercially kitted). | Open Hardware |

### Laser Cutters & Engravers

| Project | Description | License |
|---------|-------------|---------|
| [Open-source Laser Cutter Designs](https://www.instructables.com/topics/open-source-laser-cutter/) | Various community laser cutter builds using diode and CO₂ laser modules. | Various |
| [NEJE / K40 Modifications](https://github.com/meerk40t/meerk40t) | Community modifications and firmware replacements for affordable K40 CO₂ laser cutters. | Various |

### Other Fabrication Hardware

| Project | Description | License |
|---------|-------------|---------|
| [Jubilee](https://github.com/machineagency/jubilee) | Open-source multi-tool motion platform from the Machine Agency (UW). Supports 3D printing, liquid handling, probing, and more. | MIT |
| [Hangprinter](https://github.com/tobbelobb/hangprinter) | Cable-suspended 3D printer with theoretically unlimited build volume. | GPL-3.0 |
| [Open Source Ecology (OSE)](https://www.opensourceecology.org/) | Global Village Construction Set — open-source blueprints for 50 industrial machines including CNC torch tables, induction furnaces, and more. | Open Hardware |

### Control Electronics

| Project | Description | License |
|---------|-------------|---------|
| [SKR series (BigTreeTech)](https://github.com/bigtreetech) | Popular open-source 32-bit 3D printer control boards. | GPL-3.0 |
| [Duet3D](https://github.com/Duet3D) | High-end open-source control boards for 3D printers and CNC machines. | GPL-3.0 |
| [Smoothieboard](https://github.com/Smoothieware/Smoothieboard) | Open-source ARM-based motion controller board. | CERN OHL |
| [Einsy RAMBo](https://github.com/ultimachine/EinsyRambo) | Prusa's control board design (RAMBo family). | GPL-3.0 |
| [RAMPS (RepRap Arduino Mega Pololu Shield)](https://reprap.org/wiki/RAMPS) | Classic Arduino-based 3D printer electronics. Foundational design. | GPL |
| [Manta series (BigTreeTech)](https://github.com/bigtreetech) | Newer generation of open-source control boards optimised for Klipper. | GPL-3.0 |
| [EBB toolhead boards (BigTreeTech)](https://github.com/bigtreetech) | CAN bus toolhead boards for Klipper-based printers. | GPL-3.0 |
| [Escher3D (Duet clones)](https://www.escher3d.com/) | Open-source Duet-compatible boards and accessories. | Various |

---

## Design Repositories & Commons

| Platform | Description |
|----------|-------------|
| [Printables](https://www.printables.com/) | Prusa's model-sharing platform. Large community with model remix tracking. |
| [Thingiverse](https://www.thingiverse.com/) | One of the oldest 3D model repositories. CC-licensed models. |
| [Thangs](https://thangs.com/) | 3D model search engine and repository with geometric search. |
| [GrabCAD](https://grabcad.com/) | Engineering-focused CAD model library. |
| [WikiFactory](https://wikifactory.com/) | Collaborative open hardware development platform. |
| [Open Source Hardware Association (OSHWA)](https://www.oshwa.org/) | Certification and registry for open-source hardware projects. |
| [FOSSEE (IIT Bombay)](https://fossee.in/) | Free and Open Source Software for Education — includes CAD/CAE resources and tutorials. |
| [NIH 3D Print Exchange](https://3dprint.nih.gov/) | Repository of biomedical 3D models. |

---

## Community & Knowledge Sharing

| Resource | Description |
|----------|-------------|
| [RepRap Wiki](https://reprap.org/wiki/) | The foundational knowledge base for open-source 3D printing — hardware, firmware, calibration, and community documentation. |
| [Klipper Documentation](https://www.klipper3d.org/) | Configuration references, tuning guides, and kinematic explanations for Klipper firmware. |
| [LinuxCNC Documentation](http://linuxcnc.org/docs/) | Comprehensive guides for CNC machine configuration and G-code programming. |
| [FreeCAD Wiki](https://wiki.freecad.org/) | Tutorials, workbench documentation, and macro libraries for FreeCAD. |
| [OpenFOAM Wiki](https://openfoamwiki.net/) | Community documentation and tutorials for OpenFOAM CFD. |
| [Voron Documentation](https://docs.vorondesign.com/) | Build guides, sourcing guides, and tuning documentation for Voron printers. |
| [Teaching Tech Calibration](https://teachingtechyt.github.io/calibration.html) | Web-based calibration toolkit for FDM 3D printers. Open source. |

---

## Supply Chain & Material Databases

| Resource | Description | License |
|----------|-------------|---------|
| [MatWeb](https://www.matweb.com/) | Material property database (free access, proprietary). | Proprietary (free) |
| [NIST Additive Manufacturing Material Database](https://ammd.nist.gov/) | Government-maintained AM materials data. | Public Domain |
| [Senvol Database](https://senvol.com/database/) | Additive manufacturing machine and material database. | Proprietary (free access) |
| [3DPrintMaterials.info](https://3dprintmaterials.info/) | Community-maintained filament and resin material profiles. | CC |
| [Open Material Database](https://github.com/ulfschneider/material) | Efforts toward open material property databases. | Various |

---

## Related Awesome Lists

- [awesome-3d-printing](https://github.com/ad-si/awesome-3d-printing) — General 3D printing resources.
- [awsomeEngSci](https://github.com/Foadsf/awsomeEngSci) — FOSS for engineering and science.
- [awesome-open-source-hardware](https://github.com/Open-Source-Hardware/awesome-open-source-hardware) — Open hardware projects.
- [awesome-robotics](https://github.com/kiloreux/awesome-robotics) — Robotics software and tools.
- [awesome-IoT](https://github.com/HQarroum/awesome-iot) — Internet of Things platforms and frameworks.
- [awesome-federated-learning](https://github.com/chaoyanghe/Awesome-Federated-Learning) — Federated learning papers and frameworks.

---

## Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a pull request.

If you know of a FOSS tool, open hardware design, or resource that belongs here, please open an issue or submit a PR. We are especially interested in:

- Tools used in real decentralised fabrication workflows
- Open firmware projects for fabrication machines
- Federated learning and distributed ML applied to manufacturing
- Open hardware designs with active communities
- Standardisation efforts for fabrication data interchange

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

This list is dedicated to the public domain under [CC0 1.0 Universal](LICENSE).

The individual tools and projects listed retain their own respective licenses as noted in the tables.
