# Curriculum Development Proposal  
## 9545 — Hands-On IoT Systems for Environmental Monitoring

**Degree Programme:** M.Sc. Information Engineering and Computer Science  
**Credits:** 5 CP  
**Total Workload:** 150 hours  
**Proposed Teaching Period:** 14 weeks  
**Planned Group Size:** approximately 25 students  

> **Working curriculum proposal for academic discussion.**  
> The purpose of this document is to define the intended scope, depth, teaching sequence, practical emphasis, and feasibility of the module before development of the full curriculum handbook.

---

# 1. Module Concept

The module **Hands-On IoT Systems for Environmental Monitoring** is designed as an applied systems-engineering course in which students learn how information originating in the physical environment is acquired, processed, communicated, stored, interpreted, and, where appropriate, converted into physical action.

The course deliberately spans several engineering domains:

**physical measurement → electronics → embedded computing → communication → distributed IoT systems → data infrastructure → visualization → decision/action**

Its purpose is not to provide specialist-level education in every individual domain. Instead, students develop sufficient competence across the complete IoT chain to understand the interactions between subsystems, make technically justified design decisions, integrate components correctly, diagnose failures, and evaluate the resulting system.

The central pedagogical principle is:

> **Introduce fundamentals quickly, then immediately apply them to a realistic IoT engineering problem.**

Accordingly, concepts such as resistors, capacitors, MOSFETs, ADCs, C data types, interrupts, MQTT, databases, or low-power states are not taught as disconnected subjects. Each is introduced because it solves a concrete systems problem.

Examples include:

- a multiplexer because the system has more sensors than available ADC channels;
- a MOSFET because a microcontroller cannot directly power a pump or fan;
- a decoupling capacitor because switching a load causes unstable supply voltage;
- PWM because an actuator requires controllable power or soft starting;
- an interrupt because event detection should not depend on continuous polling;
- a watchdog because an unattended monitoring node must recover from firmware failure;
- deep sleep because a battery-powered sensor must operate for months;
- LoRaWAN because a remote sensor cannot reach available Wi-Fi;
- MQTT because several consumers need access to the same observations;
- metadata because the value `24.3` by itself is not a meaningful environmental observation;
- calibration because digitally stored data is not automatically trustworthy data.

The course therefore develops **systems competence rather than technology-specific competence alone**.

A defining feature of the module is that **environmental monitoring is used as the coherent application domain, while the underlying engineering architecture is deliberately transferable to other cyber-physical IoT systems**.

The same fundamental pattern:

**sense → process → communicate → interpret → act**

appears in many application domains, including:

- smart buildings: occupancy, HVAC, lighting, and indoor-air-quality systems;
- Industry 4.0: condition monitoring, industrial sensors, machine telemetry, and predictive-maintenance inputs;
- smart agriculture: soil sensing, irrigation, greenhouse control, and weather monitoring;
- smart cities: distributed air-quality, noise, lighting, traffic, and infrastructure sensing;
- energy systems: smart metering, photovoltaic monitoring, battery monitoring, and distributed energy assets;
- logistics: cold-chain monitoring, asset tracking, and condition monitoring;
- home automation: lighting, HVAC, security, and energy management;
- wearable and healthcare-related sensing, while recognizing that medical applications introduce additional regulatory, safety, validation, and privacy requirements.

The module therefore teaches **general cyber-physical IoT engineering through environmental monitoring**, rather than limiting students to environmental-monitoring technology alone.

---

# 2. Position within the M.Sc. Programme

Although several fundamental electrical and programming concepts may first be encountered at Bachelor level, their inclusion does not make this an undergraduate course.

Students entering an interdisciplinary M.Sc. Information Engineering and Computer Science programme may have substantially different previous education. A student from computer science may be comfortable with software architecture but have limited practical electronics experience. A student from electrical engineering may understand circuits but have less experience with databases, distributed messaging, APIs, or IoT data infrastructure.

The course therefore creates a common engineering foundation before requiring students to reason at system level.

The Master's-level component is primarily expressed through the students' ability to:

- compare alternative architectures rather than simply reproduce a tutorial;
- quantify performance, power consumption, and measurement quality;
- justify component, protocol, and architectural choices;
- analyze failure modes and limitations;
- integrate heterogeneous technologies;
- evaluate scalability and maintainability;
- distinguish a functioning prototype from a reliable monitoring system;
- defend technical decisions using measurements, datasheets, and engineering reasoning.

A simple task such as connecting a temperature sensor to an ESP32 is not Master's-level work.

Designing an autonomous monitoring system and being able to explain why a particular sensor, sampling interval, MCU, communication technology, data model, and power architecture were selected (and what happens when any of them fails) is.

---

# 3. Transferability Beyond Environmental Monitoring

Environmental monitoring provides a particularly suitable teaching context because it naturally combines physical sensing, embedded systems, low-power operation, communication, spatial and temporal data, long-term reliability, and real-world deployment.

However, the engineering concepts taught in the module are intentionally transferable.

The course should therefore repeatedly show students where the same design pattern appears in other domains.

| Course principle | Environmental example | Transfer example |
|---|---|---|
| ADC and signal conditioning | water-quality or analog climate sensor | industrial pressure or vibration transducer |
| Multiplexing | many soil or environmental channels | building-automation or battery-monitoring channels |
| MOSFET switching | irrigation pump or ventilation fan | HVAC actuator, lighting, or industrial load |
| PWM | environmental fan or pump control | motor soft start or variable-speed ventilation |
| Interrupts | rain-gauge pulse or event sensor | encoder, machine event, or access sensor |
| Low-power sleep | remote weather station | logistics tracker, smart meter, or wearable |
| RS-485 / Modbus | environmental instrumentation | industrial machine and process instrumentation |
| BLE | nearby environmental sensor | wearable or room-level sensing |
| LoRaWAN | distributed air-quality or soil nodes | smart-city sensing or utility metering |
| MQTT | environmental observation network | building or factory telemetry |
| Time-series database | temperature or air-quality history | PV monitoring or machine-condition history |
| Spatial data | distributed pollution measurements | smart-city infrastructure or asset mapping |
| Fail-safe control | irrigation or ventilation | HVAC, industrial actuation, or energy systems |
| Battery budgeting | remote sensor station | asset tracker or autonomous field device |
| Sensor drift and calibration | air-quality or water sensor | industrial condition-monitoring instrumentation |

The teaching pattern should normally be:

1. introduce the **environmental monitoring problem**;
2. teach the underlying engineering principle;
3. apply it in the laboratory;
4. briefly show one or two **transfer applications** in another IoT domain.

This reinforces that students are learning reusable engineering patterns rather than a collection of domain-specific recipes.

Healthcare and safety-critical industrial systems should be presented only as transfer examples. The module does not claim to qualify students to independently engineer regulated medical devices or safety-rated industrial control systems.

---

# 5. External Academic Benchmark

The proposed scope was compared with current Master's-level IoT, embedded-systems, and environmental-monitoring courses at other universities.

The closest primary comparisons are:

1. **University of Southampton — Foundations of Embedded IoT Systems**
2. **University of Genoa — Distributed Electronic Systems and Technologies for Environmental Monitoring**

Additional supporting comparisons are provided by:

3. **Hochschule Osnabrück — Internet of Things**
4. **ETH Zürich — Enabling Smart and Low Power IoT Sensor Nodes**
5. **University of Bologna — Internet of Things**

## 3.1 University of Southampton — Foundations of Embedded IoT Systems

The University of Southampton's Level-7 module **Foundations of Embedded IoT Systems** has a published total workload of **150 hours**.

Its syllabus includes:

- embedded-IoT system architecture;
- microcontrollers;
- sensors and actuators;
- power supplies;
- embedded programming in C;
- data representation and structures;
- memory-mapped I/O;
- peripherals;
- timers and interrupts;
- software debugging;
- low-power design;
- power budgeting;
- duty cycling;
- batteries and energy harvesting;
- MQTT;
- CoAP;
- LoRaWAN;
- 6LoWPAN.

Its published workload includes:

| Southampton activity | Hours |
|---|---:|
| Lectures | 30 |
| Practical classes/workshops | 15 |
| Tutorials | 6 |
| Preparation | 15 |
| Independent study | 20 |
| Assessment | 40 |
| Revision | 24 |
| **Total** | **150** |

This provides a particularly useful benchmark because the total workload is identical to the proposed HSRW module.

Southampton is comparatively stronger in:

- embedded software;
- IoT operating systems;
- software-development tooling;
- network technologies.

The proposed HSRW module is comparatively stronger in:

- practical electronics;
- signal acquisition;
- measurement quality;
- power-electronics literacy;
- environmental deployment;
- end-to-end sensor-to-database integration.

The two curricula therefore overlap strongly in **embedded processing, low-power design, communication, and system reasoning**, while placing different emphasis on the physical measurement and data-infrastructure ends of the system.

## 3.2 University of Genoa — Distributed Electronic Systems and Technologies for Environmental Monitoring

The University of Genoa offers a **5-credit Master's module** specifically focused on distributed electronic systems and technologies for environmental monitoring.

Its published learning objectives explicitly begin with basic electronic and sensing principles and progress toward distributed environmental-monitoring systems.

The curriculum includes concepts such as:

- electrical variables;
- current, voltage, power, and energy;
- resistive circuits;
- RC circuits;
- semiconductor devices;
- sensors and sensing methods;
- embedded electronic systems;
- signal acquisition;
- electronic interfaces;
- analog-to-digital conversion;
- distributed IoT environmental monitoring.

This benchmark is especially important because it demonstrates that revisiting electrical and electronics fundamentals inside a Master's environmental-monitoring module is academically defensible.

The proposed HSRW course follows a similar physical-to-digital progression in its first block, but then continues farther into:

- embedded C;
- low-power firmware;
- communication technologies;
- MQTT;
- distributed IoT architecture;
- data storage;
- interoperability;
- visualization;
- system reliability.

Genoa therefore provides a useful benchmark for the **INPUT / measurement chain**, while Southampton provides a particularly strong benchmark for the **PROCESSING & COMMUNICATION** portion.

## 3.3 Hochschule Osnabrück — Internet of Things

Hochschule Osnabrück's Master's module **Internet der Dinge** is worth **5 ECTS** with a total workload of **150 hours**.

Its published structure includes:

- 15 hours lecture;
- 15 hours supervised small-group work;
- 15 hours seminar;
- 75 hours small-group independent work;
- 15 hours literature study;
- 10 hours preparation/follow-up;
- 5 hours presentation preparation.

Its content includes:

- IoT concepts;
- interaction with the real world;
- IoT wireless technologies;
- network design;
- IoT security;
- edge and cloud architectures;
- data acquisition;
- data processing;
- high-level data management;
- data analysis;
- system integration.

This is particularly relevant because it confirms that a **45-hour lecturer-supported / 150-hour total workload model** is realistic for a German Master's-level 5-ECTS IoT module.

## 3.4 ETH Zürich — Enabling Smart and Low Power IoT Sensor Nodes

ETH Zürich offers **Enabling Smart and Low Power IoT Sensor Nodes**, a practical 4-credit course.

Its stated learning objectives include:

- firmware programming;
- sensor acquisition;
- signal processing;
- digital interfaces;
- Bluetooth;
- Wi-Fi;
- low-power sensor-node engineering;
- practical C programming on real devices.

The course reinforces the relevance of combining:

**MCU + sensor + firmware + communication + low-power operation**

at advanced university level.

The proposed HSRW module has a broader end-to-end systems scope, while ETH's offering places particularly strong emphasis on practical embedded experimentation.

## 3.5 University of Bologna — Internet of Things

The University of Bologna's 6-credit Master's IoT course covers a broad end-to-end system perspective including:

- electronic circuit basics;
- sensors and actuators;
- embedded systems;
- wireless technologies;
- BLE;
- LoRaWAN;
- MQTT;
- CoAP;
- HTTP;
- sensor-data management;
- time-series databases;
- Grafana;
- edge/cloud architectures;
- advanced data analysis.

This demonstrates that a Master's IoT course can legitimately cover the complete chain from physical sensing to backend processing, provided individual technologies are taught at different depths.

## 3.6 Comparative Position of the Proposed HSRW Module

A useful summary is:

| Dimension | Proposed HSRW | Southampton | Genoa | Osnabrück | ETH | Bologna |
|---|---|---|---|---|---|---|
| Electrical fundamentals | Medium–High | Low–Medium | High | Low | Medium | Low–Medium |
| Sensor interfacing | High | Medium | High | Medium | High | Medium |
| Embedded C | High | High | Medium | Medium | High | Medium |
| Low-level MCU concepts | High | High | Medium | Medium | High | Medium |
| Timers / interrupts | High | High | Lower emphasis | Medium | High | Medium |
| Low-power design | High | High | Lower emphasis | Medium | High | Medium |
| Power architecture | Medium | Medium | Medium | Low–Medium | Medium | Low |
| Wireless IoT | High | High | Medium | High | Medium | High |
| Distributed messaging | High | High | Lower emphasis | High | Lower emphasis | High |
| Databases / data pipeline | Medium | Low | Low | High | Low | High |
| Environmental-monitoring focus | Core | Application area | Core | Application area | Application area | Application area |
| Hands-on system integration | Very high | High | Medium–High | High | Very high | High |

This table is (an own self) **curriculum interpretation**, not an official ranking.

The proposed HSRW course can therefore be understood as combining:

> **Genoa-style physical measurement and sensing foundations**  
> +  
> **Southampton/ETH-style embedded and low-power competence**  
> +  
> **Osnabrück/Bologna-style IoT integration and data-system perspective**

while deliberately limiting specialist depth in each individual subdiscipline.

---

# 5. Course Architecture

The course is organized into three major blocks.

## Part I — INPUT: Sense, Measure and Interface

Students learn how a physical phenomenon becomes reliable digital information.

The progression is:

**physical phenomenon → sensor → electrical signal → conditioning → conversion → digital interface**

This block establishes sufficient electronics competence to prevent students from treating sensor modules as unexplained black boxes.

## Part II — PROCESSING & COMMUNICATION: Compute, Control and Connect

Students learn what happens inside the embedded system and how a standalone measurement becomes part of a distributed system.

The progression is:

**digital observation → MCU → embedded C → timing/control → power management → communication → networked IoT**

The emphasis moves gradually from constrained 8-bit systems and low-level programming toward contemporary 32-bit connected MCUs.

## Part III — OUTPUT & SYSTEM INTEGRATION: Act, Store, Visualize and Evaluate

Students integrate the physical and digital system.

The progression is:

**observation → communication → structured data → persistent storage → visualization → decision → optional physical actuation**

Reliability, security, calibration, and failure analysis are incorporated to distinguish a real monitoring system from a laboratory demonstration.

---

# 6. Depth Model

Because the module is only 5 CP, not every subject can be treated at specialist depth.

Three explicit levels are therefore proposed.

## M — Mastery

Students must understand the concept and independently demonstrate practical competence.

Examples:

- basic circuit reasoning;
- multimeter use;
- MOSFET switching;
- ADC interpretation;
- embedded C data representation;
- timers and interrupts;
- PWM;
- low-power duty cycling;
- communication trade-offs;
- MQTT;
- structured sensor data;
- fault handling.

## L — Engineering Literacy

Students must understand what the technology does, recognize when it is appropriate, interpret relevant specifications, and integrate an existing solution.

Examples:

- operational amplifiers;
- instrumentation amplifiers;
- external ADCs;
- buck/boost converters;
- CAN;
- NB-IoT/LTE-M;
- PostGIS;
- SensorThings;
- motor-driver ICs.

Students are not expected to derive or design these technologies from first principles.

## A — Advanced / Extension

These subjects belong to project extensions, later electives, or specialist study.

Examples:

- precision analog-front-end design;
- switching-converter compensation design;
- RF/antenna design;
- advanced control theory;
- RTOS internals;
- secure-boot/PKI architecture;
- PCB EMC optimization;
- database performance engineering;
- TinyML/computer vision.

This distinction is essential to keeping the course realistic within 150 hours.

---

# 7. Recommended Weekly Teaching Format

The existing module specifies **60 TU** of teaching time.

At 45 minutes per TU:

$$
60 \times 45\,\text{min} = 2700\,\text{min} = 45\,\text{h}
$$

A recommended structure is therefore:

- **14 weeks × 3 contact hours = 42 hours**
- **3-hour final project demonstration and technical defence**

giving:

$$
42\,\text{h} + 3\,\text{h} = 45\,\text{h}
$$

This matches the existing 60-TU teaching-time requirement.

The normal weekly format is proposed as:

### Approximately 2 hours lecture / guided engineering session

The lecture should not consist exclusively of conventional presentation slides. Worked calculations, component demonstrations, datasheet interpretation, engineering comparisons, and short design problems should occur during this period.

### Approximately 1 hour focused laboratory

The laboratory should apply the most important principle of the lecture immediately.

Laboratories should use prepared hardware and software baselines. Students should spend their limited laboratory time **measuring, programming, debugging, and reasoning**, rather than repeatedly installing software or assembling unnecessarily complicated infrastructure.

The ratio can be flexed locally while retaining the same total contact time.

Examples:

- electronics/soldering week: 90 min lecture + 90 min lab;
- communication-comparison week: 135 min lecture + 45 min lab;
- low-power measurement week: 90 min lecture + 90 min lab;
- database-architecture week: 135 min lecture + 45 min integration lab.

The module therefore does not require every week to follow an identical minute-by-minute structure.

---

# 8. Detailed 14-Week Curriculum

# WEEK 1 — Environmental Monitoring as an Engineering System

## Main question

**How does a physical environmental phenomenon become information?**

### Lecture

The course begins with complete system architecture rather than immediately introducing a microcontroller.

Example monitoring systems include:

- microclimate monitoring;
- air quality;
- indoor environmental quality;
- soil and agricultural monitoring;
- water monitoring;
- urban heat;
- noise;
- weather;
- energy/environment interactions.

Students examine the complete chain:

**environment → sensor → electronics → MCU → communication → data → interpretation**

The electrical fundamentals required for later work are then rapidly established:

- voltage;
- current;
- resistance;
- electrical power;
- energy;
- Ohm's law;
- series and parallel connections;
- ground and common ground;
- short circuit versus open circuit;
- floating inputs;
- pull-up and pull-down resistors;
- electrical measurement using a multimeter.

### Laboratory

Students receive a low-voltage circuit containing an LED, resistor, switch/input, and power supply.

They must:

- measure supply voltage;
- calculate and verify resistor behaviour;
- measure current;
- identify ground;
- create and correct a floating input;
- implement a pull-up or pull-down;
- diagnose intentionally introduced faults.

### Depth

**M:** voltage, current, resistance, power, Ohm's law, common ground, pull-up/down, multimeter.

**L:** Kirchhoff laws sufficient for simple circuit reasoning.

**A:** network-analysis techniques beyond the needs of IoT nodes.

### Main work

**Measure instead of guess.**

Students begin using an engineering notebook or Git-based project log.

### Project connection

Teams identify the environmental phenomenon their semester project will monitor and define the first measurable variables.

### Transfer beyond environmental monitoring

The same measurement-chain reasoning applies to smart-building sensors, industrial condition monitoring, energy metering, logistics trackers, and connected home systems.

---

# WEEK 2 — Components, Switching and Practical Hardware

## Main question

**How does a low-power processor safely interact with real electrical loads?**

### Lecture

The most important common electronic components are introduced through their IoT functions.

### Resistors

- current limiting;
- pull-up/down;
- voltage division;
- sensing.

### Capacitors

- decoupling;
- bulk capacitance;
- basic filtering;
- energy storage;
- why a capacitor is placed close to an IC.

### Diodes

- protection;
- flyback;
- reverse-polarity concept.

### Transistors

BJT operation is introduced briefly.

MOSFETs receive greater attention:

- gate, drain, source;
- switching behaviour;
- logic-level MOSFET;
- gate resistor;
- pull-down;
- $R_{DS(on)}$;
- switching loads.

Power dissipation is introduced using:

$$
P \approx I^2R
$$

Thermal behaviour is connected to:

- device heating;
- package limitations;
- heat sinks;
- reliability.

### Laboratory

Students:

- solder a small circuit (after a bread board);
- inspect solder joints;
- perform continuity testing;
- drive a low-voltage fan or similar load through a MOSFET;
- add flyback protection where appropriate;
- observe the difference between powering a load directly and controlling it through an appropriate switching stage.

### Depth

**M:** resistors, capacitors, diode protection, MOSFET switching, soldering.

**L:** BJT behaviour, thermal resistance, heat-sink selection.

**A:** transistor device physics, MOSFET gate-driver optimization.

### Main work

**Build and physically debug a circuit.**

### Project connection

Students establish the electrical requirements of sensors and any potential actuators.

### Transfer beyond environmental monitoring

The same MOSFET, protection, and thermal principles appear when driving HVAC fans, lighting loads, industrial solenoids, pumps, and low-voltage automation hardware.

---

# WEEK 3 — Sensors, Analog Signals and Measurement Quality

## Main question

**When a computer displays 23.47 °C, how trustworthy is that number?**

### Lecture

The distinction between **data resolution and measurement quality** becomes central.

Topics include:

- analog versus digital sensors;
- sensor transfer functions;
- accuracy;
- precision;
- repeatability;
- resolution;
- drift;
- noise;
- bias;
- calibration;
- plausibility;
- environmental influences.

Signal conditioning is introduced at application level:

- RC filtering;
- buffering;
- amplification;
- operational-amplifier purpose;
- instrumentation-amplifier purpose;
- bridge-sensor concept.

ADC principles include:

$$
N = 2^n
$$

quantization levels and approximately:

$$
\Delta V = \frac{V_{\text{ref}}}{2^n}
$$

Voltage-reference stability is linked directly to measurement reliability.

### Laboratory

Students read an analog environmental sensor or generated analog signal.

They:

- inspect raw measurements;
- calculate theoretical ADC resolution;
- introduce or observe noise;
- apply simple filtering;
- compare raw and processed values;
- perform a simple calibration or two-point correction.

### Depth

**M:** ADC, resolution, reference voltage, noise, filtering, calibration.

**L:** op-amps, instrumentation amplifiers, bridge sensors.

**A:** precision analog design, advanced noise analysis.

### Main work

**Determine whether a measurement is believable.**

### Project connection

Teams select their principal sensor and document:

- range;
- accuracy;
- resolution;
- interface;
- expected environmental limitations.

### Transfer beyond environmental monitoring

Signal conditioning, calibration, and ADC reasoning transfer directly to industrial pressure sensors, strain gauges, battery-monitoring circuits, energy sensors, and many wearable-sensing systems.

---

# WEEK 4 — Digital Sensors, Buses and Expanding I/O

## Main question

**How can many different devices communicate with one constrained controller?**

### Lecture

Students study:

- GPIO;
- UART;
- I²C;
- SPI;
- 1-Wire concept;
- addressing;
- timing;
- bus topology;
- communication errors.

The lecture then introduces ways of overcoming limited MCU resources:

- analog multiplexer;
- demultiplexer concept;
- shift register;
- GPIO expander;
- external ADC.

A major secondary learning outcome is **datasheet literacy**.

Students learn where to find:

- operating voltage;
- absolute maximum ratings;
- pinout;
- logic levels;
- current consumption;
- communication timing;
- addressing;
- recommended application circuits.

### Laboratory

Students connect multiple sensors to an MCU and inspect bus activity using a logic analyzer.

A deliberate fault such as:

- wrong address;
- missing pull-up;
- incorrect wiring;
- incorrect bus speed

must be diagnosed.

### Depth

**M:** UART, I²C, SPI, and datasheet use.

**L:** 1-Wire, MUX, GPIO expanders, external ADCs.

**A:** writing generic bus drivers from first principles.

### Main work

**Use a datasheet to make unfamiliar hardware work.**

### Project milestone 1

Teams demonstrate reliable sensor acquisition.

### Transfer beyond environmental monitoring

The same I²C, SPI, UART, multiplexer, and GPIO-expansion patterns appear in smart-building controllers, industrial sensor hubs, robotics, battery-management systems, and connected appliances.

---

# WEEK 5 — Inside the Microcontroller

## Main question

**What does a microcontroller actually do underneath a high-level framework?**

### Lecture

Students begin with a constrained 8-bit or similarly transparent MCU environment.

Topics include:

- CPU;
- RAM;
- Flash;
- clock;
- registers;
- GPIO;
- peripherals;
- memory-mapped I/O;
- binary;
- hexadecimal;
- bit masks;
- AND;
- OR;
- XOR;
- shifts.

Students perform simple register-level operations rather than relying exclusively on high-level GPIO functions.

The point is not that future projects must use an 8-bit MCU.

The point is to expose what modern abstractions hide.

### Laboratory

Students:

- configure GPIO using registers;
- manipulate individual bits;
- read a digital input;
- inspect a register map;
- implement a small hardware-control exercise without a high-level GPIO abstraction.

### Depth

**M:** registers, bit operations, binary/hexadecimal reasoning, GPIO.

**L:** detailed CPU architecture.

**A:** assembly-language programming and instruction-pipeline analysis.

### Main work

**Understand the processor underneath the framework.**

### Project connection

Students define what local processing their environmental node requires.

### Transfer beyond environmental monitoring

Register-level MCU understanding transfers directly to industrial controllers, smart meters, connected appliances, low-level robotics, automotive-adjacent embedded systems, and dedicated sensor devices.

---

# WEEK 6 — Embedded C and Representation of Physical Information

## Main question

**How does a constrained processor represent and calculate real-world quantities safely?**

### Lecture

Topics include:

- `uint8_t`;
- `uint16_t`;
- `uint32_t`;
- signed and unsigned values;
- numerical limits;
- overflow;
- casting;
- arrays;
- structures;
- pointers;
- `volatile`;
- memory awareness;
- fixed-point arithmetic.

A specific conceptual exercise demonstrates how an 8-bit CPU can process numbers larger than 255 by performing multiple operations and propagating carry between bytes.

This leads naturally into sensor representation.

Instead of storing:

$$
23.47
$$

as floating point, for example, an embedded system might store:

$$
2347
$$

as hundredths of a degree.

Students discuss the trade-offs between:

- range;
- precision;
- memory;
- execution cost;
- readability;
- overflow risk.

### Laboratory

Students intentionally produce and diagnose overflow.

They then:

- implement a multi-byte counter;
- represent environmental values using fixed-point arithmetic;
- construct a sensor-observation `struct`;
- encode status conditions as bit flags.

### Depth

**M:** integer types, overflow, fixed point, structures, and practical pointer use.

**L:** compiler implementation and memory layout.

**A:** architecture-specific optimization.

### Main work

**Make data representation an engineering decision.**

### Project connection

Students define how measurements, timestamps, and status data are represented inside their firmware.

### Transfer beyond environmental monitoring

Safe integer representation, overflow handling, fixed-point arithmetic, and compact status encoding are equally relevant in smart meters, asset trackers, battery systems, motor controllers, and other constrained embedded devices.

---

# WEEK 7 — Time, Events, PWM and Robust Firmware

## Main question

**How can an embedded system perform several jobs without simply waiting?**

### Lecture

Topics include:

- blocking versus non-blocking software;
- hardware timers;
- counters;
- interrupts;
- ISR limitations;
- periodic sampling;
- PWM;
- inrush current / startup surge current;
- duty cycle;
- PWM frequency;
- soft start;
- watchdog timers;
- finite-state machines.

PWM is expressed as:

$$
D = \frac{t_{\text{on}}}{T}
$$

The same concept is applied to:

- LED intensity;
- fan speed;
- motor power;
- heating;
- controlled startup.

The watchdog is presented through a practical question:

> What happens if a monitoring station installed several kilometres away freezes?

### Laboratory

Students replace blocking code with timer/event-based behaviour.

They:

- generate hardware PWM;
- implement a soft-start ramp;
- respond to an external interrupt;
- intentionally freeze firmware;
- demonstrate watchdog recovery.

### Depth

**M:** timer, interrupt, PWM, watchdog, state-machine concept.

**L:** detailed timer peripheral architectures.

**A:** RTOS scheduling.

### Main work

**Build firmware that continues to work without constant human intervention.**

### Project milestone 2A

Teams demonstrate non-blocking embedded acquisition and local processing.

### Transfer beyond environmental monitoring

Timers, interrupts, PWM, state machines, and watchdogs are core patterns in HVAC control, industrial automation, robotics, motor control, smart appliances, and building systems.

---

# WEEK 8 — Low-Power IoT Systems

## Main question

**How can an environmental node operate for months or years instead of hours?**

This is a core signature topic of the module.

### Lecture

Students begin from:

$$
P = VI
$$

and:

$$
E = Pt
$$

For duty-cycled operation:

$$
I_{\text{avg}} =
\frac{\sum_{i=1}^{n} I_i t_i}{T}
$$

Approximate ideal battery life is introduced as:

$$
t_{\text{battery}}
\approx
\frac{C_{\text{battery}}}{I_{\text{avg}}}
$$

Topics include:

- active mode;
- idle;
- sleep;
- deep sleep;
- RTC wake-up;
- timer wake-up;
- external-interrupt wake-up;
- comparator/threshold wake-up;
- sensor-triggered wake-up;
- peripheral shutdown;
- switching sensor power;
- always-on domains;
- current profiling;
- sensor warm-up time;
- radio duty cycling;
- leakage;
- quiescent current.

Students learn a characteristic environmental-IoT workflow:

**sleep → wake → sense → process → communicate → sleep**

rather than simply keeping every subsystem powered continuously.

### Laboratory

Students measure the current consumption of an intentionally inefficient node.

They then modify it to:

- sleep;
- wake periodically;
- enable sensor;
- measure;
- communicate;
- disable unnecessary peripherals;
- return to sleep.

Current consumption before and after optimization is compared.

### Depth

**M:** sleep/wake architecture, duty cycling, current measurement, and energy budgeting.

**L:** specific MCU power states and power-domain architecture.

**A:** custom ultra-low-power always-on hardware.

### Main work

**Measure where the energy goes.**

### Project connection

Teams produce the first quantitative power budget for their system.

### Transfer beyond environmental monitoring

The same sleep–wake architecture is fundamental to smart meters, logistics trackers, BLE beacons, battery-powered building sensors, remote industrial monitors, and many wearable devices.

---

# WEEK 9 — Power Architecture for Autonomous Nodes

## Main question

**How should a sensor node actually be powered?**

### Lecture

Relevant battery technologies are introduced at engineering-literacy level:

- alkaline;
- NiMH;
- lithium-ion / LiPo;
- LiFePO₄ concept;
- solar-assisted systems.

Power conversion includes:

### LDO

With approximate conceptual efficiency under simplified conditions:

$$
\eta_{\text{LDO}}
\approx
\frac{V_{\text{out}}}{V_{\text{in}}}
$$

### Buck converter

Used when:

$$
V_{\text{out}} < V_{\text{in}}
$$

### Boost converter

Used when:

$$
V_{\text{out}} > V_{\text{in}}
$$

### Buck-boost converter

Relevant where the source voltage can move above and below the required system voltage.

Students additionally encounter:

- conversion efficiency;
- quiescent current;
- dropout;
- brownout;
- battery monitoring;
- charger-IC concept;
- load switching;
- solar charging at architectural level.

### Laboratory

Students compare two regulator approaches using actual voltage, current, and efficiency measurements.

Efficiency is calculated as:

$$
\eta =
\frac{P_{\text{out}}}{P_{\text{in}}}
$$

A design scenario such as:

**12-V solar/battery system → 3.3-V IoT node**

is evaluated.

### Depth

**M:** power-budget reasoning and architecture selection.

**L:** LDO, buck, boost, buck-boost, and battery charging.

**A:** designing switching regulators, magnetics, or feedback compensation from first principles.

### Main work

**Select a power architecture based on measurements and requirements.**

### Project milestone 2B

Teams present:

- power source;
- regulator choice;
- average-current estimate;
- expected battery life;
- main uncertainty in that estimate.

### Transfer beyond environmental monitoring

Power-source selection and regulator trade-offs recur in autonomous logistics devices, PV monitoring, battery systems, building sensors, connected appliances, and portable cyber-physical systems.

---

# WEEK 10 — Communication Technologies and Engineering Trade-Offs

## Main question

**How should environmental observations leave the device?**

### Lecture

The communication stack is deliberately separated into levels.

### Local interfaces

- UART;
- I²C;
- SPI.

### Industrial/wired communication

- RS-485;
- Modbus RTU;
- CAN concept.

### Wireless communication

- Wi-Fi;
- BLE;
- LoRa/LoRaWAN;
- NB-IoT/LTE-M conceptually.

Technologies are evaluated against:

- power consumption;
- range;
- bandwidth;
- latency;
- infrastructure;
- topology;
- reliability;
- cost.

Students should understand that there is no universally superior communication technology.

A camera node and a remote soil-moisture node may require entirely different solutions.

### Laboratory

Rather than implementing every protocol, students work with selected examples.

A suitable combination would be:

- communicate with one industrial/RS-485 device;
- implement or evaluate one wireless connection;
- compare alternatives for several deployment scenarios.

### Depth

**M:** selecting and justifying a communication architecture.

**L:** RS-485/Modbus plus major wireless technologies.

**L/A:** CAN and cellular IoT depending on available hardware.

**A:** RF and antenna design.

### Main work

**Choose technology based on constraints rather than familiarity.**

### Project connection

Teams finalize and defend the communication architecture of their monitoring system.

### Transfer beyond environmental monitoring

The same communication trade-offs appear in Industry 4.0, smart buildings, smart-city infrastructure, logistics, utility metering, agriculture, and home automation.

---

# WEEK 11 — MQTT and Distributed IoT Architecture

## Main question

**How does a sensor node become part of a distributed information system?**

### Lecture

Students now move from connectivity to messaging.

MQTT topics include:

- broker;
- client;
- publisher;
- subscriber;
- topic structure;
- wildcards;
- QoS;
- retained messages;
- Last Will;
- authentication;
- reconnection;
- session behaviour;
- duplicate observations;
- offline buffering.

MQTT is compared with HTTP/REST.

CoAP is introduced at engineering-literacy level.

The larger conceptual distinctions are:

**publish/subscribe versus request/response**

and:

**edge processing versus remote/cloud processing**

At this stage students may transition to a more powerful connected 32-bit MCU where appropriate, allowing direct comparison with the constrained system used earlier.

### Laboratory

Students publish environmental data to a broker and subscribe from another client.

The network is deliberately interrupted.

Students must examine:

- reconnection;
- data loss;
- retained data;
- unexpected disconnection;
- Last Will behaviour.

### Depth

**M:** MQTT architecture, topic design, and resilient behaviour.

**L:** HTTP/REST.

**L/A:** CoAP.

### Main work

**Design communication that remains meaningful when networks are unreliable.**

### Project milestone 3

The project must now autonomously:

**sense → process → communicate**

### Transfer beyond environmental monitoring

MQTT and similar distributed messaging patterns are widely reusable in factory telemetry, building management, home automation, energy systems, fleet/logistics monitoring, and other event-driven IoT architectures.

---

# WEEK 12 — Output, Actuation and Safe Failure

## Main question

**When the system decides to act, how can it do so safely?**

### Lecture

Relevant outputs include:

- LEDs;
- indicators;
- relays;
- MOSFET-controlled loads;
- fans;
- pumps;
- valves;
- DC motors;
- servos.

Students receive application-level understanding of:

- H-bridges;
- motor-driver ICs;
- threshold control;
- hysteresis;
- open-loop operation;
- basic closed-loop concept.

Hysteresis is introduced through an environmental example.

Rather than continuously switching a fan around one exact threshold:

- **turn ON above 27 °C**
- **turn OFF below 24 °C**

The most important element of the lecture is failure behaviour.

Students analyze:

- sensor disconnected;
- implausible measurement;
- communication lost;
- controller restarted;
- actuator stuck;
- stale data.

The concepts of fail-safe and safe default behaviour are introduced.

### Laboratory

Students create a low-voltage sensor-controlled actuator.

The sensor is then deliberately disconnected or manipulated.

Students must specify and implement the appropriate failure behaviour.

### Depth

**M:** safe switching, threshold/hysteresis, and failure reasoning.

**L:** H-bridges and dedicated motor drivers.

**A:** PID and advanced control theory.

### Main work

**Design the failure case before celebrating the successful case.**

### Project connection

Projects may integrate an actuator where scientifically or technically meaningful.

Actuation is not mandatory for projects whose purpose is solely observation.

### Transfer beyond environmental monitoring

Thresholds, hysteresis, safe defaults, and actuator supervision transfer directly to HVAC control, lighting, industrial machinery, smart appliances, energy-management systems, and agricultural automation.

---

# WEEK 13 — From Measurements to Information

## Main question

**What information must accompany a number before it becomes a useful environmental observation?**

### Lecture

Students begin with the deliberately incomplete value:

```text
23.4
```

and determine what is missing.

A useful observation may require:

- measured property;
- value;
- unit;
- timestamp;
- sensor identifier;
- location;
- calibration information;
- quality flag;
- provenance.

A structured representation could resemble:

```json
{
  "node": "KL-07",
  "property": "airTemperature",
  "value": 23.4,
  "unit": "degC",
  "timestamp": "2026-06-15T14:02:30Z",
  "sensor": "SHT45-07",
  "location": "campus-west",
  "quality": "valid"
}
```

Structured payloads such as JSON are introduced.

Students then distinguish between:

- relational databases;
- time-series databases;
- spatial databases.

PostGIS is introduced because environmental observations are often geographically referenced.

OGC SensorThings is introduced as an example of interoperability and standardized representation of sensors, observed properties, locations, and observations.

Implementation tools may include:

- Node-RED;
- a prepared time-series database;
- PostgreSQL/PostGIS where appropriate;
- Grafana;
- maps;
- alerts;
- API access.

Tools are treated as implementations of architecture rather than learning objectives in themselves.

### Laboratory

Students receive a prepared backend environment.

They construct or complete:

**sensor → MQTT → integration/validation → database → dashboard**

rather than spending the laboratory installing infrastructure.

### Depth

**M:** structured observations, timestamps, metadata, and complete data pipeline.

**L:** relational vs. time-series vs. spatial databases, PostGIS, and SensorThings.

**A:** database administration, replication, and query optimization.

### Main work

**Turn measurements into interoperable information.**

### Project milestone 4

Teams demonstrate the complete end-to-end pipeline.

### Transfer beyond environmental monitoring

The same structured-data, time-series, spatial, API, and dashboard concepts appear in smart buildings, PV and battery monitoring, industrial telemetry, logistics, utility systems, and smart-city platforms.

---

# WEEK 14 — Reliability, Security and Trustworthy Environmental Data

## Main question

**What happens when the real world stops behaving like the laboratory?**

### Lecture

The final week combines three related concerns.

## Data quality

- missing observations;
- sensor drift;
- outliers;
- implausible values;
- stale measurements;
- calibration;
- timestamp problems.

## System reliability

- power loss;
- network failure;
- broker failure;
- MCU crash;
- sensor failure;
- full memory;
- clock errors;
- device replacement.

## Security

- authentication;
- credentials;
- access control;
- TLS concept;
- exposed services;
- physical access;
- firmware-update concept;
- basic secrets management.

Students additionally consider:

- scalability;
- maintainability;
- monitoring/observability;
- component replacement;
- lifecycle cost.

### Laboratory — Break the System

Groups receive one or more deliberately induced faults:

- sensor disconnected;
- network disabled;
- broker restarted;
- impossible value introduced;
- clock changed;
- packet duplicated;
- MCU stalled;
- database unavailable.

Students must:

1. detect the fault;
2. explain the evidence;
3. restore operation;
4. explain how the architecture could tolerate or prevent the problem.

### Depth

**M:** fault handling, plausibility, recovery, and basic IoT security.

**L:** TLS implementation, OTA updates, and device identity.

**A:** secure boot, hardware security modules, PKI architecture, and advanced threat modelling.

### Main work

**Demonstrate that the system is trustworthy, not merely functional.**

### Transfer beyond environmental monitoring

Reliability, observability, authentication, data quality, and failure recovery are universal concerns across industrial IoT, energy systems, smart buildings, logistics, connected homes, and other cyber-physical applications.

---

# 9. Semester Project

The semester project runs alongside the course rather than being introduced at the end.

Teams develop an environmental IoT system implementing the following chain where relevant:

**environmental phenomenon → sensor → interface → MCU → embedded processing → communication → MQTT/API → storage → visualization/interpretation**

with optional:

**decision → actuation**

Possible project domains include:

- microclimate;
- indoor environment;
- air quality;
- soil conditions;
- water parameters;
- greenhouse monitoring;
- urban environmental monitoring;
- weather;
- environmental noise;
- energy/environment interaction.

The project should preferably operate outside the laboratory for several days before final submission.

The deployment period is pedagogically important because it exposes students to problems that prepared laboratory exercises cannot reproduce reliably:

- communication outages;
- unexpected resets;
- sensor drift;
- condensation or environmental exposure;
- battery behaviour;
- incorrect timestamps;
- missing observations;
- radio coverage;
- long-term data accumulation.

---

# 10. Project Milestones

## Week 2 — Problem and Requirements

Environmental question, intended user, measurable quantities, and preliminary architecture.

## Week 4 — Measurement Prototype

Reliable sensor acquisition with basic data-quality discussion.

## Week 7 — Embedded Prototype

Non-blocking embedded processing and appropriate data representation.

## Week 9 — Energy and Power Review

Measured current, duty cycle, proposed power source, and estimated operating lifetime.

## Week 11 — Connected Node

Reliable communication and demonstrated recovery from network interruption.

## Week 13 — End-to-End System

Sensor through database and visualization operational.

## Weeks 13–14 — Realistic Deployment

System operates under realistic conditions and collects data.

## Final — Engineering Demonstration and Defence

Students explain and defend:

- sensor selection;
- sampling strategy;
- MCU selection;
- power architecture;
- communication technology;
- data representation;
- system limitations;
- reliability;
- security;
- measurement quality.

---

# 11. Individual Competency Assurance

The project may be performed in teams, but individual competence must be verified.

This is particularly important because interdisciplinary teams can otherwise allow one student to perform all electronics work while another performs all software work.

Competence should therefore be progressively signed off during normal laboratory sessions rather than requiring numerous separate formal examinations.

## Hardware competency

Student demonstrates:

- correct multimeter use;
- simple resistor calculation;
- pull-up/down reasoning;
- purpose of decoupling;
- safe MOSFET switching;
- flyback protection;
- basic soldering;
- continuity/fault testing;
- ability to retrieve essential information from a datasheet.

## Embedded competency

Student demonstrates:

- bit manipulation;
- register-level GPIO;
- fixed-width integer reasoning;
- overflow diagnosis;
- timer usage;
- interrupt;
- PWM;
- non-blocking/state-machine reasoning.

## Energy and communication competency

Student demonstrates:

- current/power calculation;
- duty-cycle calculation;
- approximate battery-life calculation;
- communication-technology comparison;
- basic MQTT publication/subscription;
- explanation of reconnect/failure behaviour.

## Systems competency

During final defence the student independently explains:

- measurement chain;
- project architecture;
- power;
- communication;
- data;
- failures;
- limitations;
- security.

---

# 12. Recommended Assessment Philosophy

The assessment should reward **engineering reasoning and demonstrated competence**, not only a polished final prototype.

A possible model is:

- **40% — Team system project and technical report**
- **20% — Individual practical competency checks**
- **20% — Individual final technical defence**
- **20% — Engineering documentation / laboratory record**

Exact percentages can be adjusted to institutional examination regulations.

A central principle should remain:

> A visually attractive dashboard cannot compensate for an incorrectly designed measurement system.

Likewise:

> Excellent electronics cannot compensate for an inability to communicate, structure, and interpret the resulting information.

---

# 13. Workload Model

Total workload:

$$
150\,\text{h}
$$

## Contact time

Fourteen regular sessions:

$$
14 \times 3\,\text{h} = 42\,\text{h}
$$

Final demonstration and defence:

$$
3\,\text{h}
$$

Total contact time:

$$
42\,\text{h} + 3\,\text{h} = 45\,\text{h}
$$

## Independent work

Remaining:

$$
150\,\text{h} - 45\,\text{h} = 105\,\text{h}
$$

A realistic allocation is:

| Independent activity | Hours |
|---|---:|
| Lecture preparation and review | 21 |
| Laboratory preparation and completion | 14 |
| Semester-project development | 45 |
| Datasheet reading and independent technical study | 10 |
| Final documentation and assessment preparation | 15 |
| **Total** | **105** |

The semester project therefore receives the largest portion of independent study.

This is intentional.

The lectures and laboratories provide the engineering toolbox; the project is where students integrate it.

---

# 14. Explicit Scope Boundaries

The following subjects are intentionally included only to the level necessary for IoT-system engineering.

## Analog electronics

Students understand buffers, amplification, filtering, and instrumentation amplifiers.

They do **not** perform a full course in operational-amplifier stability, frequency response, or precision analog design.

## Power electronics

Students can choose between LDO, buck, boost, and buck-boost solutions and evaluate losses.

They do **not** design switching converters from first principles.

## RF engineering

Students compare wireless technologies and make deployment decisions.

They do **not** design RF front ends or antennas.

## Control

Students understand threshold control, hysteresis, and safe failure.

They do **not** undertake a full control-theory curriculum.

## Databases

Students understand appropriate storage models and use a prepared database infrastructure.

They do **not** become database administrators.

## Cybersecurity

Students understand essential device/network security practices.

Advanced embedded security should remain a dedicated cybersecurity topic.

## RTOS

RTOS concepts can be introduced as an extension once firmware complexity justifies them.

A complete RTOS curriculum is outside the core module.

## Computer vision / TinyML

These remain legitimate advanced environmental-monitoring project pathways but should not consume a compulsory core week.

---

# 15. Equipment and Infrastructure Philosophy

The course should not require expensive custom hardware for every student.

A reusable kit can provide:

- constrained MCU/development board;
- modern connected 32-bit MCU;
- breadboard/prototyping materials;
- common resistors/capacitors/diodes;
- logic-level MOSFET;
- environmental sensors;
- analog sensor or potentiometer/signal source;
- multiplexer or GPIO expander;
- low-voltage fan/motor/pump;
- communication interface such as RS-485;
- wireless capability;
- battery/power components.

Laboratory infrastructure should provide access to:

- multimeters;
- bench power supplies;
- soldering equipment;
- oscilloscopes;
- logic analyzers;
- current/power measurement;
- LoRaWAN or equivalent infrastructure if used.

Where practical, students should be allowed to take the core equipment kit home for project development.

---

# 16. Expected Graduate Profile After the Module

A successful student should not simply be able to say:

> “I have used an ESP32, MQTT and Grafana.”

The intended graduate should instead be able to examine an environmental-monitoring problem and reason through:

## Sensing

What should be measured, with what accuracy and sampling frequency?

## Electronics

How is the sensor interfaced, protected, and powered?

## Processing

How should the MCU represent and process the data?

## Timing

Should behaviour be polling-, timer-, or interrupt-driven?

## Power

How long must the node operate, and where is energy being consumed?

## Communication

Which network technology best fits the range, bandwidth, latency, infrastructure, and energy constraints?

## Information

What metadata is necessary for the observation to remain meaningful?

## Storage

What kind of database is appropriate?

## Reliability

What happens if the sensor, network, power supply, or software fails?

## Security

Who may communicate with or control the device?

## Evaluation

How trustworthy, scalable, and maintainable is the complete system?

That integrated reasoning ability is the principal learning outcome of the module.

The intended competence is explicitly **transferable beyond environmental monitoring**. A successful graduate should be able to recognize the same architecture in applications such as:

- smart buildings;
- industrial IoT and Industry 4.0;
- smart agriculture;
- smart cities;
- energy systems;
- logistics and asset monitoring;
- home automation;
- selected wearable and healthcare-adjacent applications, subject to additional domain-specific regulation and safety requirements.

Environmental monitoring is therefore the **coherent teaching domain**, not the boundary of the graduate's IoT competence.

---

# 17. Overall Feasibility Assessment

The proposed curriculum is **ambitious but realistic for 5 CP** under three conditions.

First, specialist technologies must remain at explicitly defined levels of depth. Students select and apply a buck converter; they do not design one. They use an instrumentation amplifier where appropriate; they do not complete a precision-analog-design curriculum.

Second, laboratories must be prepared around focused engineering challenges. A 60-minute laboratory cannot afford 40 minutes of software installation or hardware setup.

Third, not every technology named in the curriculum must be physically implemented by every student. Students should obtain **mastery of transferable principles and selected implementations** while gaining engineering literacy about alternatives.

With those controls, the breadth becomes an advantage rather than a weakness.

The module's distinctive educational identity can therefore be summarized as:

> **A hands-on cyber-physical IoT systems course taught through the coherent application domain of environmental monitoring.**

A complementary formulation is:

> **From physical phenomenon to trustworthy information and action: designing, building, and critically evaluating complete IoT systems.**

Its value within the M.Sc. Information Engineering and Computer Science programme lies precisely in connecting domains that are often taught separately: physical sensing, electronics, embedded computing, communication, and information systems.

The module does not aim to produce a specialist analog engineer, power-electronics engineer, firmware engineer, network architect, and database engineer in five credits.

It aims to produce an **information engineer who understands how all of those disciplines meet inside a real IoT system and can competently build, measure, debug, and defend that system.**

---

# 18. Primary References for Curriculum Benchmarking

The benchmark information in this proposal was checked against official university course pages available in October 2026.

1. **University of Southampton — Foundations of Embedded IoT Systems (ELEC6254), 2026/27**  
   https://www.southampton.ac.uk/courses/2026-27/modules/elec6254

2. **University of Genoa — Distributed Electronic Systems and Technologies for Environmental Monitoring, 2026/27**  
   https://corsi.unige.it/en/off.f/2026/ins/98971

3. **Hochschule Osnabrück — Internet of Things (11M0706), Version 2026**  
   https://www.hs-osnabrueck.de/en/module/11m0706/

4. **ETH Zürich — P&S: Enabling Smart and Low Power IoT Sensor Nodes, Spring Semester 2026**  
   https://vorlesungen.ethz.ch/Vorlesungsverzeichnis/lerneinheit.view?lang=en&lerneinheitId=199633&semkez=2026S

5. **University of Bologna — Internet of Things (81683), Academic Year 2025/26**  
   https://www.unibo.it/en/study/course-units-transferable-skills-moocs/course-unit-catalogue/course-unit/2025/479055

---

# 19. Recommended Next Development Stage

This proposal defines the **what**, **why**, **depth**, and overall **teaching sequence** of the module.

The next stage should be a full curriculum handbook or teaching specification of approximately 50–60 pages containing, for each week:

- precise learning objectives;
- prerequisite concepts;
- concept-dependency map;
- proposed lecture sequence;
- approximate time allocation within each class;
- worked examples;
- essential equations;
- laboratory setup;
- expected observations;
- fault-injection exercises;
- component and hardware requirements;
- datasheets to be used;
- common student misconceptions;
- mastery/literacy/advanced boundaries;
- individual competency checks;
- homework or self-study tasks;
- links to the semester project;
- assessment rubrics;
- recommended literature and technical standards.

The handbook should also explain **why the sequence is pedagogically structured as it is**, for example:

- why measurement and electronics precede microcontrollers;
- why constrained/8-bit processing precedes modern 32-bit abstraction;
- why timers and interrupts precede low-power operation;
- why low-power firmware precedes power-architecture selection;
- why physical communication precedes MQTT;
- why data modelling follows reliable acquisition and communication;
- why reliability and security conclude the system-level progression.

The result should function not merely as a syllabus but as an **academic design specification and practical teaching guide for the complete module**.
