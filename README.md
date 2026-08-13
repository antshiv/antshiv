# 🌍 ANTSHIV ROBOTICS
## **Autonomous Flight Systems and CPU-Native AI**

![Lab Illustration](assets/lab_illustration.jpg)

> Building the mathematics, embedded control, test systems, and CPU AI needed for autonomous machines.

**🧭 Mission**

I am developing two connected engineering systems: an autonomous aircraft stack built from flight mathematics through physical test rigs and custom electronics, and C-Kernel-Engine, a CPU-native AI runtime for inference and training research.

The aircraft must remain safe without AI or network connectivity. CKE can later add onboard perception and connect the aircraft to larger distributed CPU ground systems. Conservation, inspection, mapping, and remote monitoring are possible applications once the underlying systems are proven.


🧩 Approach

Vertical integration from mathematics to hardware:
Flight dynamics → embedded control → propulsion and test rigs → CPU AI → integrated autonomous systems.
I build and validate the stack one boundary at a time.

---

## 🎯 Current Technical Focus

**🚁 Autonomous Aerial Platforms**
Real-time INS, quaternion mathematics, state estimation, rotor dynamics, and control systems for autonomous flight. The work spans desktop mathematical references, embedded firmware, physical test rigs, custom flight-controller electronics, and eventually an integrated aircraft.

**⚡ CPU AI Inference and Training**
Building [**C-Kernel-Engine (CKE)**](https://github.com/C-Kernel-Engine/C-Kernel-Engine), a CPU-native runtime and kernel compiler for transformer language, vision, and audio models. CKE turns explicit model circuits into generated C and validates them against established numerical oracles. *The long-term purpose is practical AI across onboard computers, ground nodes, and distributed CPU systems.*

---

## 🗂️ Navigating My Repositories

**Full-Stack Flight Controller (WIP)** — [attitudeMathLibrary](https://github.com/antshiv/attitudeMathLibrary) • [stateEstimation](https://github.com/antshiv/stateEstimation) • [dynamic_models](https://github.com/antshiv/dynamic_models) • [controlSystems](https://github.com/antshiv/controlSystems) • [inertial_navigation_system](https://github.com/antshiv/inertial_navigation_system) • [AeroDynControlRig](https://github.com/antshiv/AeroDynControlRig) (OpenGL+ImGui simulator)

**Embedded Systems** — [BLEDroneCode](https://github.com/antshiv/BLEDroneCode) (NRF53 drone: Zephyr RTOS, sensor drivers, PWM motor control) • [HandheldController](https://github.com/antshiv/HandheldController) (wireless integration with drone controller)

**Hardware Test Rigs** — [ThrustStand](https://github.com/antshiv/ThrustStand) (propulsion characterization) • [DroneTestRig](https://github.com/antshiv/DroneTestRig) (multi-axis dynamic testing)

**CPU AI** — [C-Kernel-Engine](https://github.com/C-Kernel-Engine/C-Kernel-Engine) (generated C inference and training research across language, vision, and audio models) • [CKE documentation](https://c-kernel-engine.github.io/C-Kernel-Engine/)

---

## 💭 How I Think

I prefer depth over hype. Gaps in my knowledge make me uneasy, which forces me to strip away abstractions and understand mechanics from first principles. I'm comfortable reading datasheets, solving problems from source truth, and moving seamlessly across the stack from low-level C/HPC to JavaScript/HTML/CSS. I use 3D printing to rapidly move from idea to prototype.

I run Linux/AwesomeWM and prefer NXP, TI, and Nordic MCUs. Datasheet fluency means I'm not limited to Arduino/ESP32/Raspberry Pi just because they're popular—I can evaluate compute requirements and pick the right chip. My repositories reflect this: lots of C code, AI augmentation, and first-principles approaches.

**A quick lab tour:** One of my hidden talents is optimizing space. The illustration above shows my closet lab—4×7 ft containing 3-4 monitors, dual laptops (Windows + Linux), 3D printer, Akro-Mils storage for electronics, microscope, soldering station, oscilloscope, signal generator, and a multi-angle YouTube capture setup. I use vertical shelving to maximize surface volume. I also love woodworking, so my miter saw and tools live on a pegboard in the same space.

![The 4×7 ft closet lab—real workspace, real work](assets/lab_web.jpg)

---

## 🗺️ Roadmap: Drone Systems and CKE

*Revised periodically based on budget, resources, time, skill development, and life obligations.*

I work in systematic cycles: build a subsystem, establish a software oracle, replay it on embedded hardware, measure it on a physical rig, and only then integrate it into a larger vehicle. Dates are targets rather than promises. Progress depends on budget, available space, field access, safety, and what each experiment teaches me.

This work does not begin from an empty lab. I already have a 3D printer, electronics bench, microscope, soldering equipment, oscilloscope, signal generator, Nordic nRF5340 and NXP i.MX RT1170 development hardware, a built thrust stand, and a multi-axis attitude rig. The immediate task is turning those individual assets into one reproducible validation system.

Lab expansion is part of that work, not a separate collection project. Purchases such as JBC soldering and rework tools, board fixtures, power instrumentation, safety equipment, or improved storage must unlock a defined flight-controller, ESC, propulsion, or compute experiment. The order is: identify the blocked measurement or assembly task, buy the minimum capability that removes it, document the procedure, and reuse it across later revisions.

**Stage 0** (2025-2027) — *Mathematics, Software and Evidence*
Unify coordinate frames, units, telemetry formats, and dependency versions across the flight-control repositories • Validate quaternion, state-estimation, control, rotor, and six-DOF implementations against independent desktop references • Add deterministic sensor replay and regression fixtures • Connect AeroDynControlRig visualizations to recorded evidence • Continue CKE numerical-parity, profiling, model-family support, training research, and distributed-runtime work

**Exit condition:** the same recorded trajectory can run through the mathematical reference, native C implementation, embedded target, and visualizer with explained tolerances and reproducible reports.

**Stage 1** (2026-2028) — *Instrumented Bench Systems*
Harden the compact lab for repeatable PCB assembly, inspection, rework, power measurement, and safe motor testing • Calibrate the thrust stand with versioned datasets • Characterize commercial motor, propeller, and ESC combinations as reference hardware • Exercise attitude and controller behaviour on the multi-axis rig • Record thrust, torque, RPM, current, voltage, temperature, vibration, and controller state • Establish safe fault handling, current limits, and emergency shutdown procedures

**Exit condition:** the lab can reproduce an assembly or measurement procedure, and measured propulsion and attitude experiments agree with the software models closely enough that a mismatch can be assigned to the model, firmware, electronics, or mechanics.

**Stage 2** (2027-2029) — *Custom Flight and Motor-Control Hardware*
Design an nRF5340 flight-controller PCB in KiCad around the validated sensor and telemetry stack • Build and review a single-channel i.MX RT1170 motor-control prototype before attempting an integrated ESC • Use the 3D printer for enclosures, fixtures, sensor mounts, and rapid form-factor iterations • Complete at least two board revisions with bring-up records, power-integrity measurements, and hardware-in-the-loop replay

**Exit condition:** the custom boards reproduce the bench reference, survive fault tests, and can be assembled and diagnosed from published design and test records.

**Stage 3** (2028-2030) — *Integrated Aircraft Prototype*
Integrate the flight controller, propulsion system, navigation sensors, power system, telemetry, and a conservative airframe • Begin with commercial propellers and controlled tethered tests • Progress through stabilization, navigation, geofencing, return-to-home, and emergency landing • Keep flight safety independent of CKE and external connectivity

**Exit condition:** repeatable, human-supervised flight with bounded behaviour when communications, companion compute, or individual sensors fail.

**Stage 4** (2029-2031) — *Onboard and Ground Intelligence*
Run compact CKE vision, audio, or classification models on onboard companion compute • Develop portable CPU ground nodes for larger models, mission analysis, and multi-aircraft coordination • Harden encrypted communication and graceful switching between onboard and ground processing • Evaluate distributed inference and training using owned CPU hardware

**Exit condition:** the aircraft remains useful offline, gains measurable capability when ground compute is available, and records complete provenance for observations, models, and decisions.

**Stage 5** (2030-2032) — *Field Applications*
Apply the proven aircraft and CPU AI system to inspection, mapping, remote monitoring, search and rescue, or conservation projects where a real partner and measurable problem exist • Establish ground truth, power, connectivity, maintenance, and operating procedures for each deployment

**Exit condition:** a partner can use the system to answer a real field problem over repeated operations, not merely watch a laboratory demonstration.

**Stage 6** (Ongoing) — *Scale What Survives Contact With Reality*
Repeat successful aircraft, CKE, and distributed-compute experiments • Improve the components that measurements identify as constraints • Expand hardware only when the previous system is understood and maintainable • Publish evidence, failures, and design changes so each cycle begins from stronger ground

Completing every stage exactly as written is unlikely. That is acceptable. The purpose of the roadmap is to choose the next useful experiment while keeping the drone and CKE work connected without creating additional programs before these two are mature.

## 🤝 Working With Me

**ANTSHIV ROBOTICS** is currently a solo operation. I use AI augmentation to accelerate development while maintaining deep technical understanding across the stack.

**Open to:**
- **Contract work** on hard embedded, control-systems, and CPU AI problems
- **Collaborations** with shared philosophy (understand first, abstract when necessary)
- **Flight and test-system development** where mathematical and physical evidence matter
- **Future field partnerships** after the underlying aircraft and compute systems are ready

**Best fit for projects requiring:**
- Understanding system constraints before choosing abstractions
- Power/compute-constrained environments
- Long-term deployment without framework dependencies

---

## 📺 Connect

- 🎥 **YouTube**: Flight controller deep-dives, sensor builds, and embedded AI walkthroughs → [@Antshiv Robotics](https://www.youtube.com/@antshivrobotics)
- 💬 **Discord**: Real-time discussions on C optimization, drone dynamics, and hardware choices → [Join here](https://discord.gg/bH34RuG2)
