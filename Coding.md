For the robot to function we had to use code.

## Our Coding App

* We decided to use Pybricks Beta as our coding app. 
* It uses the programming language Python and even comes with its documentary.

## Our Coding Language

We used Python as our programming language. Here are some reasons why.

* One reason why we chose Python is because it is very precise. It's useful when having to do something at just the right distance.
* Another reason is that Python is a standard programming language.
  It is used all around the world, and many engineering jobs and robotics jobs require Python coding.
* And finally it has reusable functions. It is useful when having to repeat a task multiple times. For example, reuseable functions are useful when having to hit a lever multiple times, so that you don't have to keep copy pasting code.

## Documenting

We spent a lot of time cleaning up and documenting our code so our fellow team members would know how the code worked.
  * We would put a comment describing what 5-6 lines did, and how it completed the mission.

## Our Code

In mission 1 we push in to the side.
# Mission #1

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
TURN_RATE = 80
TURN_ACC = 85


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
left_attachent_motor = Motor(port=Port.B)
right_attachent_motor = Motor(port=Port.A)

# VARIABLES (SENSORS)
# ===================
right_color_sensor = ColorSensor(Port.E)
left_color_sensor = ColorSensor(Port.F)


# FUNCTIONS
# =========

# solve mission 13
# ----------------
def solve_mission_13_and_return_to_base():
    # Settings for drivebase
    drivebase.settings(straight_speed=STRAIGHT_SPEED,
                       straight_acceleration=STRAIGHT_ACC,
                       turn_rate=TURN_RATE,
                       turn_acceleration=TURN_ACC)
    drivebase.straight(200)
    drivebase.turn(-90)
    drivebase.straight(700)
    drivebase.turn(95)
    drivebase.straight(155)
    right_attachent_motor.run_angle(speed=1000, rotation_angle=1650,
                                    then=Stop.COAST, wait=True)
    drivebase.straight(-155)
    drivebase.turn(-90)
    drivebase.straight(300)
    drivebase.turn(-90)
    drivebase.straight(200)
    drivebase.turn(-90)
    drivebase.straight(200)
    drivebase.turn(-90)


# MAIN PROGRAM
# ============
solve_mission_13_and_return_to_base()
```

In mission 6 we push into the light show and then we do lights and sound.
# Mission 6

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
left_attachent_motor = Motor(port=Port.B)
right_attachent_motor = Motor(port=Port.A)

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
    drivebase.straight(690)
    # Turn to face mission
    drivebase.turn(40)
    # Drive into mission
    drivebase.straight(230)
    # Do the speakers
    left_attachent_motor.run_angle(speed=1000, rotation_angle=-270,
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

In mission 3 we push the flaps up.
# Mission 3 

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
TURN_RATE = 80
TURN_ACC = 85


# VARIABLE (HUB)
# ==============
hub = InventorHub()

# VARIABLES (DRIVING MOTORS + DRIVEBASE)
# ==============================
left_motor = Motor(port=Port.D, positive_direction=Direction.COUNTERCLOCKWISE)
right_motor = Motor(port=Port.C)
drivebase = DriveBase(left_motor, right_motor, 56, 110)

# VARIABLES (ATTACHMENT MOTORS)
# =============================
left_attachent_motor = Motor(port=Port.B)
right_attachent_motor = Motor(port=Port.A)

# VARIABLES (SENSORS)
# ===================
right_color_sensor = ColorSensor(Port.E)
left_color_sensor = ColorSensor(Port.F)


# FUNCTIONS
# =========

def solve_mission_4():
    drivebase.settings(straight_speed=900,
                       straight_acceleration=300,
                       turn_rate=100,
                       turn_acceleration=85)
    drivebase.straight(distance=550, then=Stop.HOLD, wait=True)
    drivebase.turn(angle=60, then=Stop.HOLD, wait=True)
    drivebase.straight(distance=150, then=Stop.HOLD, wait=True)
    drivebase.turn(angle=30, then=Stop.HOLD, wait=True)
    drivebase.straight(distance=570, then=Stop.HOLD, wait=True)
    drivebase.turn(angle=-90, then=Stop.HOLD, wait=True)
    drivebase.straight(distance=190, then=Stop.HOLD, wait=True)
    drivebase.straight(distance=-190, then=Stop.HOLD, wait=True)
    drivebase.turn(angle=43, then=Stop.HOLD, wait=True)
    drivebase.straight(distance=235, then=Stop.HOLD, wait=True)
    drivebase.turn(angle=80, then=Stop.HOLD, wait=True)
    drivebase.straight(distance=900, then=Stop.HOLD, wait=True)
    drivebase.turn(angle=90, then=Stop.HOLD, wait=True)
    drivebase.straight(distance=1220, then=Stop.HOLD, wait=True)


# MAIN PROGRAM
# ============
solve_mission_4()
```

In mission 11 we spin the wheel on the top.
# Mission 11

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
TURN_RATE = 80
TURN_ACC = 85


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
left_attachent_motor = Motor(port=Port.B)
right_attachent_motor = Motor(port=Port.A)

# VARIABLES (SENSORS)
# ===================
right_color_sensor = ColorSensor(Port.E)
left_color_sensor = ColorSensor(Port.F)


# FUNCTIONS
# =========

# solve mission 13
# ----------------
def solve_mission_13_and_return_to_base():
    # Settings for drivebase
    drivebase.settings(straight_speed=STRAIGHT_SPEED,
                       straight_acceleration=STRAIGHT_ACC,
                       turn_rate=TURN_RATE,
                       turn_acceleration=TURN_ACC)
    drivebase.straight(200)
    drivebase.turn(-90)
    drivebase.straight(700)
    drivebase.turn(95)
    drivebase.straight(155)
    right_attachent_motor.run_angle(speed=1000, rotation_angle=1650,
                                    then=Stop.COAST, wait=True)
    drivebase.straight(-155)
    drivebase.turn(-90)
    drivebase.straight(300)
    drivebase.turn(-90)
    drivebase.straight(200)
    drivebase.turn(-90)
    drivebase.straight(200)
    drivebase.turn(-90)


# MAIN PROGRAM
# ============
solve_mission_13_and_return_to_base()
```

