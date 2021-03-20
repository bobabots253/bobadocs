# Intro to Sensors

So now you have the basic sense of what electronics does and have looked at some of the tools that they use. Very nice. Now you can look at one of the most important aspects of Electronics: dealing with sensors. There are a myraid of things you can do with sensors and there are many different types of sensors. There are a lot of sensors and we will never use all of them at one time when making a robot, let alone do everything we possibly can with them at one time. However, there are some sensors you should know about and other pieces of info that you should know when dealing with sensors in electronics. Lets take a look.

### LiDar

A LiDAR(Light Detection And Ranging) sensor emits pulsed light waves into the surrounding environment. The pulses bounce off the objects and return to the sensor. Then, the sensor calculates the time it took to create an estimate of what objects look like and where they are (think echolocation but with lasers light pulses).

These are useful for measuring the distances between the sensor and the object. For example, it can be equipped on drones to survey the terrain and create a 3d model.

![LiDAR modelling](assets/images/frc/LiDAR_model.png)

*Example of LiDAR Model*

Using LiDAR can get you precise data quickly (It repeats millions of processes at once to create an accurate 3D map on a computer). Not only that, but the lasers are eye-safe so no one's getting hurt looking at a sensor.

### Optical Encoder

Optical Encoders are made up of four components: a light source, a sensor, a movable disk, and a fixed mask. Rotary encoders use a sensor to identify position change as light passes through a patterned encoder wheel or disk. It detects when light has passed through or not, with the rate of light passing through and being blocked being measured. Forces such as velocity, rotation, and position can be measured using an optical encoder.

![Optical Encoder](assets/images/frc/optical-encoder)

*Example of an Optical Encoder*

Can measure multiple types of motion. For example, the speed of a wheel on a car or robot can be measured. The rate at which the light is allowed through and is blocked is measured, providing for the speed of the wheel.

Though this can account for precise motion measurement, it has problems with debris and environments (light, smoke). This is because it can make it harder for light to be detected from the sensor.