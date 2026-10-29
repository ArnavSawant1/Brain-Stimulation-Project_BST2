# Project status and open decisions — October 2026

## What is shown in the supplied material
- Isolated PCB region around Raspberry Pi Pico, U3 REF3025, U4 AD5662, and J2 analog connector.
- Capacitors C6/C7/C8 near the DAC/reference circuit; their visible roles are bypass/reference decoupling, not proof of a complete band-pass filter.
- Screenshot of shopping cart listing ISO1642, AD5662, RP2040 Pico, OPA197, resistors, capacitors and headers.
- JLCPCB production dashboard shows **94%** in the captured image, with final inspection checked and transport to warehouse as the current stage; this does not confirm delivery.

## Critical discrepancy: band-pass filter
The active band-pass filter is **not visible** in the provided close-up of the manufactured board design. A filter BOM does not establish that footprints and nets are included. Check the full schematic and layout before claiming the band-pass filter was integrated.

## Design review checklist
- [ ] Obtain schematic, PCB and LTspice originals
- [ ] Identify filter topology, supply rails, expected signal level and load
- [ ] Confirm component footprints match exact purchased manufacturer parts
- [ ] Check proper isolated supply return and ground-boundary rules
- [ ] Run schematic ERC and board DRC; review safety-critical nets
- [ ] Independently review output protection and isolation assumptions
- [ ] Compare LTspice simulation to non-human bench measurement

## Change control
Keep the first manufactured PCB documented as **Rev A / original prototype** until exact revision identifiers can be confirmed. Create a new revision for any added filter stage; do not alter historical files without noting revision.
