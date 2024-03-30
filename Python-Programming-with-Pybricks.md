# Python Programming with Pybricks

We have decided to use Python instead of Scratch because Python is reusable, standard, and precise. We can all __understand the code better when coding with Python__.

## Why Use Pybricks

![Pybricks](Media/Images/Learned-Tools/Pybricks.png)

[__Pybricks__](https://pybricks.com) is the __best open-source Python library for programming LEGO robots__. It has many powerful functionalities such as running multiple programs and controlling the drivebase with advanced movements.

## How We Have Used Pybricks in FLL

We have used Pybricks to code our competition bot, and it has been a fantastic experience. We have coded programs that enable our robot to perform specific tasks, such as going to the mission, doing it, and returning to the home area.

You can see [__all of our Pybricks code shared openly on GitHub__](https://github.com/Noddin-RobotMakers/RobotMakers-FLLChallenge-Masterpiece). Some examples are also presented below for your easy reference.

## Testing

Even with Pybricks, we have had to spend many hours testing and changing the parameters for our missions. But, with patience and perseverance, we have been able to get it right. Pybricks has __made it easy for us to test and debug our code__, allowing us to get closer to our desired outcome.

## Our Code

### Mission #1

In Mission #1 we leave a big attachment there, which pushes down the orange lever.

```python
# IMPORTS
# =======
from pybricks.hubs import InventorHub
from pybricks.pupdevices import Motor, ColorSensor
from pybricks.parameters import Direction, Port, Stop
from pybricks.robotics import DriveBase


# CONSTANTS for Robot Operation Parameters
# ========================================
STRAIGHT_SPEED = 900
STRAIGHT_ACC = 900
TURN_RATE = 900
TURN_ACC = 300


# VARIABLES Representing Robot Electronics
# ========================================

# Hub
hub = InventorHub()

# Driving Motors & Drivebase
left_motor = Motor(port=Port.D, positive_direction=Direction.COUNTERCLOCKWISE)
right_motor = Motor(port=Port.C)
drivebase = DriveBase(left_motor, right_motor, 56, 110)

# Attachment Motors
left_attachment_motor = Motor(port=Port.B)
right_attachment_motor = Motor(port=Port.A)

# Sensors
right_color_sensor = ColorSensor(Port.E)
left_color_sensor = ColorSensor(Port.F)


# FUNCTIONS Representing Robot Behaviors
# ======================================

# Solve Mission #1 and Return to Base
def solve_m1_and_return_to_base():
    # Settings for drivebase
    drivebase.settings(straight_speed=STRAIGHT_SPEED,
                       straight_acceleration=STRAIGHT_ACC,
                       turn_rate=TURN_RATE,
                       turn_acceleration=TURN_ACC)

    # Drive forward
    drivebase.straight(distance=400, then=Stop.HOLD, wait=True)
    # Drive backward
    drivebase.straight(distance=-40, then=Stop.HOLD, wait=True)
    # Drive forward
    drivebase.straight(distance=60, then=Stop.HOLD, wait=True)
    # Turn
    drivebase.turn(-15)

    # Drive backward to base
    drivebase.straight(distance=-400, then=Stop.HOLD, wait=True)


# MAIN PROGRAM
# ============
solve_m1_and_return_to_base()
```

### Mission #6

In Mission #6 we deliver a expert and audience member and push into the Light Show. We also do the Lights and Sounds.

```python
# IMPORTS
# =======
from pybricks.hubs import InventorHub
from pybricks.pupdevices import Motor, ColorSensor
from pybricks.parameters import Direction, Port, Stop
from pybricks.robotics import DriveBase


# CONSTANTS for Robot Operation Parameters
# ========================================
STRAIGHT_SPEED = 900
STRAIGHT_ACC = 300
TURN_RATE = 900
TURN_ACC = 300


# VARIABLES Representing Robot Electronics
# ========================================

# Hub
hub = InventorHub()

# Driving Motors & Drivebase
left_motor = Motor(port=Port.D, positive_direction=Direction.COUNTERCLOCKWISE)
right_motor = Motor(port=Port.C)
drivebase = DriveBase(left_motor, right_motor, 56, 110)

# Attachment Motors
left_attachment_motor = Motor(port=Port.B)
right_attachment_motor = Motor(port=Port.A)

# Sensors
right_color_sensor = ColorSensor(Port.E)
left_color_sensor = ColorSensor(Port.F)


# FUNCTIONS Representing Robot Behaviors
# ======================================

# Solve Mission #6
def solve_m6():
    # Settings for drive
    drivebase.settings(straight_speed=STRAIGHT_SPEED,
                       straight_acceleration=STRAIGHT_ACC,
                       turn_rate=TURN_RATE,
                       turn_acceleration=TURN_ACC)

    # Drive forward
    drivebase.straight(850)
    # Drive back
    drivebase.straight(-140)
    # Turn to face mission
    drivebase.turn(40)
    # Drive into mission
    drivebase.straight(230)
    # Do the speakers
    left_attachment_motor.run_angle(speed=1000, rotation_angle=-270,
                                    then=Stop.COAST, wait=True)
    # Drive back
    drivebase.straight(-100)


# Return to Base
def return_to_base():
    # Turn
    drivebase.turn(-60)
    # Drive back to home
    drivebase.straight(-1300)


# MAIN PROGRAM
# ============
solve_m6()
return_to_base()
```

### Missions #3 & #2

In Missions #3 & #2 combined, we push the flaps up and push the orange bar down on Mission #2.

```python
# IMPORTS
# =======
from pybricks.hubs import InventorHub
from pybricks.pupdevices import Motor
from pybricks.parameters import Direction, Port, Stop
from pybricks.robotics import DriveBase
from pybricks.tools import wait


# CONSTANTS for Robot Operation Parameters
# ========================================
STRAIGHT_SPEED = 900
STRAIGHT_ACC = 300
TURN_RATE = 70
TURN_ACC = 80


# VARIABLES Representing Robot Electronics
# ========================================

# Hub
hub = InventorHub()

# Driving Motors & Drivebase
left_motor = Motor(port=Port.D, positive_direction=Direction.COUNTERCLOCKWISE)
right_motor = Motor(port=Port.C)
drivebase = DriveBase(left_motor, right_motor, 56, 110)

# Attachment Motors
left_attachment_motor = Motor(port=Port.B)
right_attachment_motor = Motor(port=Port.A)


# FUNCTIONS Representing Robot Behaviors
# ======================================

# Solve Missions #3 and #2
def solve_missions_3_2():
    drivebase.settings(straight_speed=STRAIGHT_SPEED,
                       straight_acceleration=STRAIGHT_ACC,
                       turn_rate=TURN_RATE,
                       turn_acceleration=TURN_ACC)

    # Drive from the home area to mission 2
    drivebase.straight(distance=610, then=Stop.HOLD, wait=True)
    # Turn
    drivebase.turn(-3)
    # Complete Mission 2
    drivebase.straight(distance=215, then=Stop.HOLD, wait=True)
    # Drive backward
    drivebase.straight(distance=-150, then=Stop.HOLD, wait=True)
    # Turn
    drivebase.turn(angle=66, then=Stop.HOLD, wait=True)
    # Drive forward
    drivebase.straight(distance=140, then=Stop.HOLD, wait=True)
    # Turn
    drivebase.turn(angle=78, then=Stop.HOLD, wait=True)
    # Drive forward
    drivebase.straight(distance=345, then=Stop.HOLD, wait=True)
    # Turn to face Mission 3
    drivebase.turn(angle=-102, then=Stop.HOLD, wait=True)
    # Complete Mission 3
    drivebase.straight(distance=320, then=Stop.HOLD, wait=True)


# Return back to base and collect Noah
def return_to_base():
    # Return to home
    drivebase.drive(speed=-900, turn_rate=27)
    # Wait
    wait(5000)


# MAIN PROGRAM
# ============
solve_missions_3_2()
return_to_base()
```
