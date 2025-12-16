# zep-inputlag-tester

Zep experiment allowing measurement of monitor input latency using a precisely timed parallel port pulse.

## Requirements

* Zep 2.6 on a computer with a parallel port. Having a parallel cable is recommended
* Light sensor with power supply (a Teensy on a breadboard will do)
* 2 or more Channel oscilloscope for measuring results
* Monitor to test

## Usage

1. Connect the monitor to be tested to the computer running zep.
2. Connect channel A of your scope to a signal and ground line of the parallel port. Any signal pin will do, but check the pinout for grounds. The connector housing is not a ground!
3. Connect channel B of the scope to the signal line of your light sensor and the ground of your power supply. Make sure your light sensor is measuring light by waving it around and reading the voltage on the scope.
4. Run `zep flash_on_key.zp` and use F11 to switch to fullscreen mode.
5. Verify that the parallel port pulse is registering by holding the shift key until screen flashes white. Set scope trigger accordingly.
6. Measurement! Set the scope to "single" mode, face the photosensor to the screen, and hold shift.

You should now have a snapshot on your scope triggered by the parallel port pulse sent out by zep. Zep will have done its best to time this pulse as close as possible to the frame being sent to the monitor. As such, the duration between this parallel pulse and the light sensor's signal rising approximates your input latency.

## Notes

* Where you hold the sensor is matters: The bottom of the screen will take longer to refresh than the top. Keep this consistent between monitors.
* If your light sensor is noisy, make sure the ground and power supply are connected correctly.
* The zep experiment flashes the screen from #111111 and #EEEEEE
