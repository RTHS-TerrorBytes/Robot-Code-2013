Robot-Code-2013
===============

Python code run on the team's 2013 robot.

The code for team 4561: the TerrorBytes is written in Python coding language.  We were able to use a wrapper online that another FIRST team created that allows us to make an executable that will run on the robot.  We think that the Python language is a better educational tool for the team because it allows not to have to worry about the lower level concepts involved with C programing while letting students get the benefit of learning the concepts of a written language.
The code that runs on our robot is organized into one main class; myRobot.  In this class are the functions to initialize the code, assign autonomous modes to different switches, and loops to accept driver input.

Description of Functions:
 - OperatorControl():  This function contains the main listening loop that responds to joystick input from the operator’s station.  This runs after the Autonomous function and manages all movement and feedback from the robot.
 - MonoStable(Joystick,Button):  One of the problems that we faced was that when we pressed a button it would fire multiple times, even if we tapped it for a quarter of a second.  The solution was the monostable which capped the amount a times a button could be pressed to one per click.  (Technically a class)
 - Move(seconds, power):  The move function accepts as its arguments the duration for which to power the drive motors, and the power to apply to the motors.
 - MoveDistance(speed, distance):  This was not an effective way to move the robot.  With the move function we calculated the distance that the robot goes on a surface.  Then we put it into this function and we thought it would work.  NOPE!
 - Turn(time, speed, direction):  The Turn function accepts as its arguments the duration for which to power the drive motors, the power to apply to the motors, and the direction (‘left’ or ‘right’) that the user wishes to turn the robot.
 - RaiseLauncher(): This raises the platform which the launcher sits on.
 - LowerLauncher():  This lowers the platform which the platform which the launcher sits on.
 - ForwardDiskLaunch():  This was the command that we used to fire the frisbee launcher on our robot.  It activates the solenoids to fire it, then it un-activates the solenoids to fire it, then it activates the solenoids to lower it, then un-activates them.  
 - RightDiskLaunch():  Disabled function does nothing.  But it would raise the platform then if would activate the solenoids that fires the right laucher and un-fires it.  Then it lowers and un-lowers the piston.
 - TurnAngle(speed, angle):    This was a similar idea to the move distance function that we create before, as before we gathered info with the Turn function.  And for many reasons it didn’t work out, just use the Turn function.

Description of Autonomous:
 - Autonomous():  This function is called when the robot begins autonomous mode.  It checks the digital inputs from the driver’s station to determine which autonomous function the driver wishes to run and executes its corresponding function.
 - AutoRightShot():  Disable function, this does the same thing as the RightDiskLaunch
 - AutoForwardShot():  This is the same thing as FowardDiskLaunch 
 - AutoForwardsBackwards():  an autonomous program that moves the robot forwards for a short distance, and then backwards for the same distance.
 - AutoPlans(): AutoPlanA - AutoPlanC are used for testing new autonomous modes

Things we should have done:
 - Wait(seconds):  This was a fatal flaw in our autonomous mode, since if we didn’t we create a way to wait, if we changed directions to quickly the robot would spin out and things would not work right.  A wait function would solve this as we could wait that issues out with a cooldown.  
 - - - - - - - - - - - THE CAKE IS A LIE - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

