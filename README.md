# Distributed ECU System – UW Bothell Formula SAE

## 1. Overview

### Purpose and Function
This project implements a distributed Electronic Control Unit (ECU) system for UW Bothell’s Formula SAE vehicle.
The system manages key aspects of the car’s control strategy, including torque vectoring, telemetry, and critical safety functions.
Designed for high-performance electric vehicle racing, this ECU system aims to provide real-time responsiveness, modularity, and robust fault handling.

> ** Project Status **  
> Development began in **June 2025**. This is an active work in progress as part of UW Bothell's Formula SAE Electrical Team.
> Expect ongoing updates as design decisions and implementation progress.

---


### Design Philosophy
Our design is driven by the need for real-time safety, lightweight modular control, and close-to-the-metal performance.
We are currently evaluating whether to implement the system in pure ARM Assembly for maximal control and optimization, or
to use C with inline assembly where necessary to improve maintainability and development speed.
Emphasis is placed on deterministic execution, low latency, and clarity of system responsibilities across distributed nodes.

---

## 2. Relevant Rules

### Key Regulations
- FSAE Electrical Rules on tractive system and control electronics
- Safety shutdown requirements and monitoring
- Vehicle control module (VCM) isolation and diagnostics

### Compliance Strategy
We plan to modularize safety-critical paths and adhere to strict separation of tractive vs. low-voltage domains.
All system components will be documented and tested to meet FSAE technical inspection requirements.

## Relevant Rules

For full technical and safety regulations, refer to the official [Formula Student Rules](https://www.imeche.org/events/formula-student/team-information/rules)
published by IMechE. Specific rule references for this subsystem will be cited in the design documentation.

---

## 3. Design Objectives and Requirements

### Performance Goals
- Sub-millisecond response time to sensor input
- Modular nodes for steering, telemetry, and torque control
- Communication latency under 5ms between modules

### Constraints and Limitations
- Hardware constraints (number of GPIO/PWM, memory)
- Time budget for firmware testing and integration
- Compliance with FSAE hardware rules

### Specifications
- ARM Cortex-M0+ or M4 microcontrollers (exact models TBD)
- CAN-based or SPI communication between subsystems
- Boot time < 1s from power-on

---

## 4. Concept Development

### Initial Ideas
- Pure assembly implementation for deterministic timing
- Centralized vs. distributed decision-making
- Low-cost PCB fabrication with hand-assembled components

### Alternative Solutions
| Option | Pros | Cons |
|-------|------|------|
| Pure ARM Assembly | Max control, efficient | Harder to maintain |
| C with inline ASM | Easier to debug, faster dev | Slightly more overhead |
| RTOS (e.g. FreeRTOS) | Task scheduling, better abstraction | May increase latency/unpredictability |

### Decision-Making Process
Currently leaning toward C with inline assembly for maintainability and the ability to bring in more contributors.
Early tests will benchmark performance in both approaches.

---

## 5. Final Design Details
*To be completed as hardware is finalized and firmware structure is built.*

---

## 6–14. [Sections Placeholder]
These sections (Analysis, Manufacturing, Integration, Testing, Lessons Learned, etc.)
will be developed in parallel with the hardware and software implementation phases.
See `/docs` for evolving notes and diagrams once available.
