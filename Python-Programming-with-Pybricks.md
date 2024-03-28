# Python Programming with Pybricks

We have decided to use Python instead of Scratch because Python is reusable, standard, and precise.
We can all understand the code better when coding with Python.

## Why use Pybricks

Pybricks is the __best open-source Python library for programming LEGO robots__. It has many powerful functionalities such as running multiple programs or advanced drivebase control.

## How we have used Pybricks in FLL

We have used Pybricks to code our competition bot, and it has been a fantastic experience. We have coded programs that enable our robot to perform specific tasks, such as going to the mission, doing it, and returning to the home area. Please see our example programs below.

## Testing

Even with Pybricks, we have had to spend many hours testing and changing the parameters for our missions. But, with patience and perseverance, we have been able to get it right. Pybricks has made it easy for us to test and debug our code, allowing us to get closer to our desired outcome.

Pybricks is a great tool for coding and robotics. Its simple interface and open-source nature make it easy to control LEGO robots. We had a fantastic experience using Pybricks to code our competition bot and look forward to using it for future projects.

## Our Code

In Mission 1 we leave a big attachment there that pushes down the orange lever

### Mission #1

```python

# IMPORTS
# =======
from pybricks.hubs import InventorHub
from pybricks.pupdevices import Motor, ColorSensor
from pybricks.parameters import Direction, Port, Stop
from pybricks.robotics import DriveBase


# CONSTANTS
# =========
STRAIGHT_SPEED = 900
STRAIGHT_ACC = 900
TURN_RATE = 900
TURN_ACC = 300


# VARIABLE (HUB)
# ==============
hub = InventorHub()

# VARIABLES (DRIVING MOTORS + DRIVEBASE)
# ======================================
left_motor = Motor(port=Port.D, positive_direction=Direction.COUNTERCLOCKWISE)
right_motor = Motor(port=Port.C)
drivebase = DriveBase(left_motor, right_motor, 56, 110)

# VARIABLES (ATTACHMENT MOTORS)
# =============================
left_attachment_motor = Motor(port=Port.B)
right_attachment_motor = Motor(port=Port.A)

# VARIABLES (SENSORS)
# ===================
right_color_sensor = ColorSensor(Port.E)
left_color_sensor = ColorSensor(Port.F)


# FUNCTIONS
# =========


# Solve mission 1
# ---------------
def solve_and_return_to_base():
    # Settings for drivebase
    drivebase.settings(straight_speed=STRAIGHT_SPEED,
                       straight_acceleration=STRAIGHT_ACC,
                       turn_rate=TURN_RATE,
                       turn_acceleration=TURN_ACC)
    # Drive forward
    drivebase.straight(distance=400, then=Stop.HOLD, wait=True)
     # Drive forward
    drivebase.straight(distance=-40, then=Stop.HOLD, wait=True)
     # Drive forward
    drivebase.straight(distance=60, then=Stop.HOLD, wait=True)
    drivebase.turn(-15) 

    # Drive forward
    drivebase.straight(distance=-400, then=Stop.HOLD, wait=True)


# MAIN PROGRAM
# ============
solve_and_return_to_base()
```

In Mission 6 we deliver a expert and audience member and push into the light show. We also did the lights and sounds.

### Mission 6

```python

# IMPORTS
# =======
from pybricks.hubs import InventorHub
from pybricks.pupdevices import Motor, ColorSensor
from pybricks.parameters import Direction, Port, Stop
from pybricks.robotics import DriveBase


# CONSTANTS
# =========
STRAIGHT_SPEED = 900
STRAIGHT_ACC = 300
TURN_RATE = 900
TURN_ACC = 300


# VARIABLE (HUB)
# ==============
hub = InventorHub()

# VARIABLES (DRIVING MOTORS + DRIVEBASE)
# ======================================
left_motor = Motor(port=Port.D, positive_direction=Direction.COUNTERCLOCKWISE)
right_motor = Motor(port=Port.C)
drivebase = DriveBase(left_motor, right_motor, 56, 110)

# VARIABLES (ATTACHMENT MOTORS)
# =============================
left_attachment_motor = Motor(port=Port.B)
right_attachment_motor = Motor(port=Port.A)

# VARIABLES (SENSORS)
# ===================
right_color_sensor = ColorSensor(Port.E)
left_color_sensor = ColorSensor(Port.F)


# FUNCTIONS
# =========

# Solve mission 6
# ---------------
def solve_mission_6():
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
    # Drive back to home
    drivebase.straight(-100)


# Return to base after completing the mission
# -------------------------------------------
def return_to_base():
    # Turn
    drivebase.turn(-60)
    # Drive back to home
    drivebase.straight(-1300)


# MAIN PROGRAM
# ============
solve_mission_6()
return_to_base()
```

In Mission 3/2 we push the flaps up and push the orange bar down on M2.

### Mission 3/2

```python

# IMPORTS
# =======
from pybricks.hubs import InventorHub
from pybricks.pupdevices import Motor, ColorSensor
from pybricks.parameters import Direction, Port, Stop
from pybricks.robotics import DriveBase
from pybricks.tools import wait


# CONSTANTS
# =========
STRAIGHT_SPEED = 900
STRAIGHT_ACC = 300
TURN_RATE = 70
TURN_ACC = 80


# VARIABLE (HUB)
# ==============
hub = InventorHub()

# VARIABLES (DRIVING MOTORS + DRIVEBASE)
# ======================================
left_motor = Motor(port=Port.D, positive_direction=Direction.COUNTERCLOCKWISE)
right_motor = Motor(port=Port.C)
drivebase = DriveBase(left_motor, right_motor, 56, 110)

# VARIABLES (ATTACHMENT MOTORS)
# =============================
left_attachment_motor = Motor(port=Port.B)
right_attachment_motor = Motor(port=Port.A)

# FUNCTIONS
# =========

# Solve mission 3
# ---------------
def solve_mission_3():
    drivebase.settings(straight_speed=STRAIGHT_SPEED,
                       straight_acceleration=STRAIGHT_ACC,
                       turn_rate=TURN_RATE,
                       turn_acceleration=TURN_ACC)                
    # Drive from the home area to mission 2
    drivebase.straight(distance=610, then=Stop.HOLD, wait=True)
    drivebase.turn(-3)
    # Drive forward
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
    # Turn to face mission 3
    drivebase.turn(angle=-102, then=Stop.HOLD, wait=True)
    drivebase.straight(distance=320, then=Stop.HOLD, wait=True)
    

# Return back to base
# -------------------


def return_to_base():
    # Return to home
    drivebase.drive(speed=-900, turn_rate=27)
    # Wait
    wait(5000)

solve_mission_3()
return_to_base()
```
