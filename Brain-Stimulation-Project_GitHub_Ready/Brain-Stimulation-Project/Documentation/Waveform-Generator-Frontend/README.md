# Waveform Generator Frontend — V3 (schematic reviewed)

Open `index.html` in any modern browser. This is a standalone simulation-only frontend; no hardware/backend connection.

## Checked sources
- BrainStim_pcbDESIGN-arnavS.kicad_sch
- BrainStim_pcbDESIGN-arnavS.kicad_pcb
- User-supplied LTspice filter screenshot

KiCad stage: C9 100 nF, R6 15.8 kΩ, R7 2.32 kΩ, C10 1 nF, U5 OPA197xD. Net names DAC_OUT, FILTER_OUT, VCTRL, +15V_ISO, -15V_ISO. J2 connects DAC_OUT and ISO_GND, not VCTRL.

The voltage model is an analytical linear RC transfer estimate for a 0.5-V peak sinusoidal input, not a calibrated or measured DAC output. Square/triangle plots are illustrative, not harmonic-correct filtered waveforms. The current request visualization responds to the slider only as an *intent illustration*; no physical current-stage model is established. Slider bounds are unverified demo ranges. No hardware emergency stop exists. Not for human or animal use.

## Version 3.1 amplitude UI fix
The current slider now automatically switches the scope to the requested-current conceptual trace. This is not a hardware current output prediction. Voltage traces remain independent of mA because no current-source transfer calibration is available.

## V3.2 frequency display fix
Scope now uses a **fixed physical time window** (default 2 ms), so the number of cycles changes with the frequency slider. Choose 10 ms, 100 ms or 1 second to inspect lower frequencies. A single screen cannot resolve 1 Hz and 30 kHz simultaneously at the same timebase; very high frequencies on a long window can visually alias, as on a sampled display. Current slider scales conceptual current preview height; frequency changes cycles; shape selector changes waveform; pause/resume, reset, and zero update preview state. No hardware control exists.
