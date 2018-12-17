Note: This machine is currently not booting. Spilled water on it, either there is hardware damage or the NVRAM needs to be reflashed. This project is on hold and source files are unattainable until I fix it. Just bought a nice heat station a few months ago...will work on it soon.<br>

3D-Draw-Program<br>
===============<br><br>
Summary<br>
This program will display graphics in a 3D format based on object position.<br>
Using normal graphics pipeline, specifically position, these will use 2 camera objects set a distance apart<br>
which will do 1 of two things:<br>
1)color glasses: red and cyan images interlaced<br>
2)frequency glasses: alternate images at set frequency<br>
3)VR: separate images in each eye (account for distance between eyes)<br>

initialize two cameras set a width apart (eye width)<br>

Override normal render<br>
*Color Draw - HLSL recommended for all draw methods<br>
  convert colors to derivatives of red and cyan (red is left, cyan for right -- standard)<br>
  interlace images<br>
*Frequency Draw - timer required in update method<br>
  if timer mod(glasses frequency) <br>
  and if last draw was !camera1<br>
  then draw camera1<br>
  else draw camera2<br>
*VR - simple, one camera to left screen, other camera to right screen. Customize distance between cameras for users (distance between eyes) to avoid nauseau and disorientation.<br>
  <br>
  
  HLSL graphics code is recommended for the color addition the rest can be written in C++ or C#...<br>
