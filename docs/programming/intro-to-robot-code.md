## Setup

In order to write and run robot code, we will need to install a few pieces of software.

### WPILib

The WPILib suite installs the IDE we write our code in as well as the tools needed to run and deploy that code to the robot.

Follow the instructions on [the official WPILib documentation](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/wpilib-setup.html) for your respective OS.
This will install WPILib and all its required tooling, as well as the VSCode IDE that we use to write code.

### Git and Github

We use Git and Github to keep track of and collaborate on code.

Follow the instructions for your respective OS to [download Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

If you do not have a [Github](https://github.com/) account, create one now.

Once you have your account, tell a programming mentor or programming lead your username so they may add you to our [GitHub organization](https://github.com/MillsRoboticsTeam253).

Next, set up your username (your real name) and email in Git by following these instructions:

- [Setting your username in Git](https://help.github.com/en/articles/setting-your-username-in-git)
- [Setting your email address in Git](https://help.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address)

## Creating a robot project

### With VSCode

Bring up the Visual Studio Code command palette with Control+Shift+P:

<img src="https://docs.wpilib.org/en/stable/_images/command-palette.png">

Then, type “WPILib” into the prompt. Since all WPILib commands start with “WPILib,” this will bring up the list of WPILib-specific VS Code commands:

<img src="https://docs.wpilib.org/en/stable/_images/wpilib-commands.png">

Now, select the “Create a new project” command:

<img src="https://docs.wpilib.org/en/stable/_images/create-new-project.png">

This will bring up the “New Project Creator Window:”

<img src="https://docs.wpilib.org/en/stable/_images/new-project-creator.png">

Some elements we care about are explained below:

1. **Project Type**: The kind of project we wish to create. Usually we want `template`.
2. **Language**: The language (C++ or Java) that will be used for this project. We will be using <span style="text-decoration: underline">Java</span>.
3. **Project Base**: The base class or example to generate the project from. Our team uses `Command Robot`. You can find the templates [here](https://github.com/wpilibsuite/allwpilib/tree/master/wpilibjExamples/src/main/java/edu/wpi/first/wpilibj/templates) and examples [here](https://github.com/wpilibsuite/allwpilib/tree/master/wpilibjExamples/src/main/java/edu/wpi/first/wpilibj/examples).
4. **Project Location**: This determines the folder in which the robot project will be located.
5. **Create New Folder**: If this is checked, a new folder will be created to hold the project within the previously-specified folder. If it is not checked, the project will be located directly in the previously-specified folder. An error will be thrown if the folder is not empty and this is not checked. *You almost always want this to be checked.*
6. **Project Name**: The name of the robot project. This also specifies the name that the project folder will be given if the Create New Folder box is checked. Our code for each year is named with the format `Code<year>` ie: `Code2020`.
7. **Team Number**: The team number for the project, which will be used for package names within the project and to locate the robot when deploying code. Our team number is `253`.

Once all the above have been configured, click “Generate Project” and the robot project will be created.

### Opening The New Project

After successfully creating your project, VS Code will give the option of opening the project as shown below. We can choose to do that now or later by typing <kbd>Ctrl-K</kbd> then <kbd>Ctrl-O</kbd> (or just <kbd>Command+O</kbd> on macOS) and select the folder where we saved our project.

Once opened we will see the project hierarchy on the left. Double clicking on a file will open that file in the editor.

## Code Structure

A typical robot project may look like [this](https://github.com/MillsRoboticsTeam253/Code2020):
```
Code2020/
├── build.gradle
├── gradle/
├── gradlew
├── gradlew.bat
├── settings.gradle
├── src/main/java/frc/robot/
│   ├── Constants.java
│   ├── Main.java
│   ├── Robot.java
│   ├── RobotContainer.java
│   ├── commands/
│   │   ├── ConveyorQueue.java
│   │   ├── Drive.java
│   │   ├── Shoot.java
│   │   └── VisionTrack.java
│   └── subsystems/
│       ├── Arm.java
│       ├── Climber.java
│       ├── Conveyor.java
│       ├── Drivetrain.java
│       ├── Intake.java
│       └── Shooter.java
└── vendordeps/
    ├── Phoenix.json
    ├── REVColorSensorV3.json
    ├── REVRobotics.json
    ├── WPILibNewCommands.json
    ├── WPILibOldCommands.json
    └── navx_frc.json
```

It's a lot, so let's break it down. This is an intro to our robot structure, so we won't go into specifics on how to actually write the code until the next section.

### Gradle

When creating a robot project, Gradle will automatically generate the files `build.gradle`, `gradle/`, `gradlew`, `gradlew.bat`, `settings.gradle`. You shouldn't ever need to touch these.
Your IDE may also generate the folders `bin/`, `build/`, `.vscode/`, and `.idea/`. It's safe to ignore these files as well.

### vendordeps

The `vendordeps/` folder in our robot code contains `.json` files that identify third party libraries we use.
You can read more about it [here](https://docs.wpilib.org/en/stable/docs/software/vscode-overview/3rd-party-libraries.html).

### src

Just like any other Java project, the `src/` directory holds all of our actual code.

```
src/main/java/frc/robot/
├── Constants.java
├── Main.java
├── Robot.java
├── RobotContainer.java
├── commands/
│   ├── ConveyorQueue.java
│   ├── Drive.java
│   ├── Shoot.java
│   └── VisionTrack.java
└── subsystems/
    ├── Arm.java
    ├── Climber.java
    ├── Conveyor.java
    ├── Drivetrain.java
    ├── Intake.java
    └── Shooter.java
```

#### Main.java

This file is autogenerated, and there is rarely any reason to touch this file at all. 
It contains the classic `main` method, which is run at startup and starts up the rest of the robot code.

#### Robot.java

This file is the control center of the robot. It has the methods that are called to run the robot.
Documentation on each of the methods within it can be found [here](https://first.wpi.edu/FRC/roborio/release/docs/java/edu/wpi/first/wpilibj/IterativeRobotBase.html).

#### Constants.java

This file contains all the numbers that don't change and are relevant to the whole robot. 
This includes all ports and joystick buttons, which correlate to motor controllers, solenoids, and commands in the code.

#### RobotContainer.java

This is where we create and store the objects for the subsystems, and set up all the controller and joystick commands that the driver uses to operate the robot.
It does not extend from any superclasses, and is mainly used as a way to separate code from `Robot.java`

#### commands/

Commands are what run the robot. For example, there may be a `RunIntake` command that runs two motors to turn the wheels that intake a game piece.

#### subsystems/

Subsystems are another name for robot mechanisms, such as a drivetrain, a shooter, an intake, or a climber. The subsystem classes contain the Objects for the motor controllers and solenoids and have methods for controlling the subsystem, which are used by commands.
