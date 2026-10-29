# Brain Stimulation Project

**Status:** Research prototype — in development; not validated for human use.

## Overview
An engineering research project exploring an isolated microcontroller-controlled analog signal-generation system, including PCB layout, DAC/reference electronics, circuit simulations, embedded firmware, and bench testing. The work is **not** a clinical device and is **not intended for connection to people**.

## Architecture (working design)
- **ESP32-S3-WROOM-1:** primary/non-isolated-side controller.
- **ISO1642:** isolation interface for digital communication between ground domains.
- **Raspberry Pi Pico / RP2040:** isolated-side controller.
- **REF3025:** 2.5 V precision reference for analog conversion.
- **AD5662:** DAC for analog waveform generation.
- **OPA197 and RC components:** proposed analog-filter stage; **not confirmed installed on the manufactured PCB**.
- Separate `GND` and `ISO_GND` regions are part of the design intent; isolation and layout must be independently reviewed.

## Current status (as documented October 2026)
| Area | Status | Evidence / next task |
|---|---|---|
| PCB design | Prototype manufacturing order placed | Images in `Documentation/Images/`; source KiCad files **still required** |
| JLCPCB manufacture | Screenshot showed 94% and final inspection checked on Oct. 28 | Shipment and delivery **not verified** |
| Components | DigiKey shopping cart screenshot available | Verify which items were actually purchased/delivered; REF3025 order previously reported pending |
| Raspberry Pi Pico firmware | Bring-up code discussed | Actual `.c`, CMake files **not included here**; add working source |
| Band-pass filter | Not visibly populated in supplied PCB region | Filter schematic, simulation, and KiCad integration **open task** |
| Testing | Planned | Only use simulations and independently appropriate non-human bench setups |

## Repository map
| Directory | Content |
|---|---|
| `Hardware/KiCad-PCB/` | Editable KiCad schematic, project, layout and manufacturing outputs |
| `Hardware/LTspice/` | Editable LTspice simulations and model dependencies |
| `Hardware/Datasheets/` | Datasheet links and documentation |
| `Firmware/ESP32-S3/` | Main-controller source |
| `Firmware/RP2040-Pico/` | Pico firmware and build instructions |
| `Documentation/Reports/` | Research reports and design notes |
| `Documentation/Presentations/` | Presentation files |
| `Documentation/Images/` | PCB views, bill of materials and manufacturing progress images |
| `Testing/` | Non-human bench test plans and results |
| `BOM/` | Bill of materials and procurement records |
| `.github/` | Contribution and issue templates |

## Getting started
1. See [`GETTING_STARTED.md`](GETTING_STARTED.md) for importing and sharing this package.
2. Add the authentic **KiCad** project `.kicad_pro`, `.kicad_sch`, `.kicad_pcb` together in `Hardware/KiCad-PCB/`.
3. Add actual **LTspice** `.asc` and custom device models in `Hardware/LTspice/`.
4. Add verified ESP32-S3 and RP2040 firmware with their build configurations.
5. Open issues for missing/unfinished features, and keep measured results distinct from planned work.

## Safety
This repository documents unfinished experimental hardware. Never treat a simulation, PCB screenshot, firmware draft, or manufacturing electrical test as evidence of safety for human use. The filter and analog output stage require independent review, appropriate protection, and documented bench verification before any further application.

## Collaboration
Keep the repository **private** initially. GitHub → Settings → Collaborators → Add people to share with an instructor or teammates. Use branches and pull requests to review changes. Do not commit credentials, personal information or procurement payment details.
