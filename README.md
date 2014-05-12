PX4ESC firmware
===============

Under construction.

### Hardware timer usage
* TIM1 - 3-phase FET bridge PWM
* TIM2 - ADC synchronization, works in lockstep with TIM1
* TIM3 - Hard real time callout interface for motor control logic (preempts the kernel)
* TIM4 - High precision timestamping for motor control logic (sub-microsecond resolution, never overflows)
* TIM5 - RC PWM input capture
* TIM6 - Unused
* TIM7 - General purpose timestamping

### Build instructions
Compiler: GCC ARM 4.6+
```bash
cd tools
./fetch_chibios.sh
./fetch_libcanaerospace.sh # Or make a symlink instead
cd ..
make RELEASE=1 # RELEASE is optional; omit to build the debug version
```
Execute `./blackmagic_flash.sh [portname]` from the `tools` directory to flash the firmware with a Black Magic Debug Probe.
