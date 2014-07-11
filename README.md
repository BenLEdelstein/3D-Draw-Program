3D-Draw-Program
===============

How can we display 3D images in a game or other media using 3D Vector Positions
/*Summary
**This program will display graphics in a 3D format based on object position.
**Using normal graphics pipeline, specifically position, these will use 2 camera objects set a distance apart
**which will do 1 of two things: 
** 1)Add red and cyan two corresponding images and then adding both images to one buffer to draw
** 2)Draw both images to screen alternating at a set frequency
**These methods are intended for two types of 3D glasses, and for a display in which the position property 
**of the objects is accessible.
*/

//Algoritm//
/**
Inputs:
*3D display active
*3D mode (color glasses/frequency glasses)
*eye width
Note: while activation and mode are set in normal menus, eye width will be set with interactive display and stored in individual user files
*Hardware: glasses frequency


Override normal Camera initializations
*   initialize two cameras set a width apart (eye width)

Override normal Draw and function
*Color Draw - HLSL recommended for all draw methods
  add red value to all pixels in one camera (right or left (what is the standard?))
  add blue to the other
  combine both into one buffer (is this really that simple?)
  draw
*Frequency Draw - timer required in update method
  if timer mod(glasses frequency) 
  and if last draw was !camera1
  then draw camera1
  else draw camera2
  
  
  HLSL is recommended for the color addition the rest can be written in C++ or C#...
