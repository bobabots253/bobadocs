# Common Issues

Below are common issues programmers face, sorted by problem type. Use the *table of contents* to navigate.

!!! hint "Restart"
	Code, electronics, and the robot can randomly stop working for no apparent reason. Consider **restarting** your computer, code, robot, or other components before attempting more intrusive troubleshootting steps.

!!! info "Software Updates"
	The issue you found might be a commonly reported bug and has already been fixed in the latest version. Check the manufacturer's github or website to view the changelog and update.

## Robot Operation
### Packet Loss
**Issue:** Loss of control of robot (jerkiness); significant delay between joystick input and corresponding action; sudden robot movements when no input is being applied. The Driver Station log file reports packet loss with orange bars with respect to time.

![Boba Bot](https://www.chiefdelphi.com/uploads/default/original/3X/b/7/b742b68df1409ddb1de0390b6493b83c028f46c8.jpeg)

**Cause:** Lost communication packets between your computer/FMS and your robot's radio and roboRIO. Additionally, your robot could have lost power for a brief period before reconnecting.

**Solution:**

- During Competition Matches: Contact the field FTA/FTAA for assistance
-  All other situations:
	- Reduce surrounding wireless interference (hotspots/Wifi APs)
	- Switch to a wired connection via USB or Ethernet		
	- Make sure the driver station laptop's battery mode is set to Performance and not Battery Saver
	- Check power/data connections between radio and VRM, radio and roboRIO, battery to VRM, and battery to roboRIO
	- Check that the ethernet port the router is connected to is not loose (consider hotgluing the connection for competition)
	- Restart router/roboRIO
	- Check for your code. Certain processes can lead to high packet loss. Common culprits include USB Cameras, badly configured PID loops, logging functions, etc. It's likely that the `periodic()` loop is taking longer than 20ms to execute

### No Communication

## Programming
### startcompetiton()
### Limelight
### PID
### CAN

## Electrical
### Battery
**Issue:** Robot is browning out and/or behaving erratically when running the robot.

**Cause:** Low battery voltage or worn out battery. Alternatively, a motor is stalling.

**Solution:** Replace the battery with a fresh one from the battery charging station. Use a battery beak to check charge % (Full Charge is 130%) and battery resistance. 

!!! hint "Battery Tips"
	- Full Charge: 130% (Anything over 115% should be enough)
	- Lower internal battery resistance is better (<0.025 ohm)
	- Check the Driver Station Log File for diagnostic information for battery voltage and power delivery via the PDP
	- Use separate batteries for competition and practice/testing
	

### Compressor
**Issue:** Compressor refusing to run even after checking the wiring and pneumatic system.

**Solution:** Make sure that the default compressor settings are not being overridden. Specifically, check that `compressor.stop()` is not present, as this will disable the automatic pressure control of the Pneumatics Control Module (PCM)

!!! note ""
	Compressors do not need to be instantiated to function at a basic level. Refer to the [Javadocs](https://first.wpi.edu/wpilib/allwpilib/docs/release/java/edu/wpi/first/wpilibj/Compressor.html) to learn about advanced compressor functionality.