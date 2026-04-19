# Benchmarks and Stability Records

## Test Environment
- OS: Windows (user daily profile)
- BIOS Version: pending capture
- GPU Driver Version: 32.0.22042.14002
- Ambient Room Temperature: not recorded
- Measurement Tool: CPUID HWMonitor 1.6.3.0
- Capture Type: Idle / desktop usage (no stress test)

## Baseline Metrics

| Metric | Value | Notes |
|---|---:|---|
| CPU Package Idle Temp | 49 C | Ryzen 5 7600X package |
| CPU CCD Idle Temp | 34 C | CCD #0 |
| CPU Core Max Idle Temp | 35 C | Core max sensor |
| CPU SoC Temp (idle) | 48 C | SoC sensor |
| CPU Package Power (idle) | 29.09 W | Background activity possible |
| GPU Global Temp (idle) | 44 C | RX 9060 XT |
| GPU Hotspot Temp (idle) | 46 C | RX 9060 XT |
| GPU Memory Junction (idle) | 64 C | VRAM clock stayed high at idle |
| GPU Board Power (idle) | 31.06 W | Radeon power telemetry |
| DIMM Temperature | 32-33 C | Both modules stable |
| Motherboard System Temp | 31 C | IT8696 sensor |
| PCH Temp | 46 C | Chipset sensor |
| Case Fan Speed | 1162-1193 RPM | FANIN1 and FANIN4 |
| +12V Rail | 12.10 V | In normal range |
| +5V Rail | 5.07 V | In normal range |
| +3.3V Rail | 3.30 V | In normal range |

## Idle Baseline Notes (2026-04-19)

- Thermal behavior is healthy for desktop idle state.
- CPU package can appear elevated at idle due to boost behavior and background services.
- GPU VRAM clock remained at ~2500 MHz and fan stop mode was active (0 RPM).
- Memory junction at 64 C is acceptable, but should be rechecked after fan curve tuning.
- Rails (+12V, +5V, +3.3V) are stable and within expected tolerance.

## Next Validation Targets

- Capture true cold-boot idle (10-minute settled desktop, no launcher apps)
- Record load tests (CPU-only, GPU-only, mixed)
- Compare memory-junction temperature before/after fan-curve adjustment
- Add SSD benchmark and game/FPS benchmark entries

## Stability Test Log

| Date | Test | Duration | Result | Peak Temp | Notes |
|---|---|---|---|---:|---|
| 2026-04-19 | Idle baseline capture | 15 min | Pass | CPU 49 C / GPU 46 C hotspot | No instability detected |
| YYYY-MM-DD | CPU stress (planned) | 30 min | pending | | |
| YYYY-MM-DD | Mixed load (planned) | 45 min | pending | | |

## Change vs Outcome

| Change | Expected Effect | Measured Outcome | Keep/Revert |
|---|---|---|---|
| Example: Fan curve update | Lower GPU temp | -4 C under load | Keep |

## Performance Summary
- Most stable profile:
- Best thermal profile:
- Best noise/performance balance:

## Next Measurements
- Add gaming workload FPS tracking
- Add long-session thermal drift checks
- Add power draw comparison before/after tuning
