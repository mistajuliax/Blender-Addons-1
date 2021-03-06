# Blender-Addons

These add-ons are provided free to use for whatever purpose provided you do no claim it as your own work and that you include a link to this site if redistributed. However, if you do find them useful and wish to show your appreciation then please consider sending a donation to https://www.paypal.me/BaldingWizard. Any donation will be received with thanks and a pledge to return a proportionate amount of effort back into the Blender community.


MathsExpression
===============
Download :
* Blender 2.79 : https://github.com/baldingwizard/Blender-Addons/raw/master/MathsExpression279.zip
* Blender 2.8  : https://github.com/baldingwizard/Blender-Addons/raw/master/MathsExpression28.zip

Allows you to simply type an equation and the add-on automatically builds the node tree for you using standard maths nodes. This allows a complicated tree to be very easily constructed and is still fully GPU compatible (since it's only using 'standard' nodes).

The following operations are currently supported :

Addition, Subtraction, Multiply, Divide, Power, Sine, Cosine, Tangent, Arcsine, Arccosine, Arctangent, Absolute, Round, Greater Than, Less Than, Greater Than or Equals, Less Than or Equals, Equals, Maximum, Minimum, Modulo, Log, atan2(x,y)

A new option is available in the Add menu of the node editor to create a New node group based on the entered expression. The node group is automatically generated based on the expression using standard Maths nodes, with the Group Input and Group Output nodes automatically updated based on the variables of the equation. Multiple expressions can be specified in one expression by listing as a comma-separated list.

Some useful examples :

* 'a+b+c+d', 'a*b*c*d' : Maths expressions with more than 2 inputs - simply list as many terms as you desire.
* '(x*x+y*y+z*z)**0.5' : Vector distance (ie, sqrt(x^2+y^2+z^2)
* 'sum=a+b+c,dist=(a**2+b**2+c**2)**0.5' : Multiple named equations - creates a node with 3 inputs and 2 outputs (named 'sum' and 'dist')
* 'sin(theta*multiplier)+amplitude*cos(phi*multiplier2)' : Example of using sin() and cos() functions

Limitations
-----------
Note that the add-on does not currently trap more than the required number of inputs to a function - ie, `sin(x,y)` is treated as valid - the second input is still passed to the Maths node but will have no effect (since 'sine' only takes a single input). Similarly, with more than two inputs the additional inputs are not currently processed - so `sin(x,y,z)` will be accepted but treated as `sin(x)`.

Future Development
------------------
* Better syntax trapping and reporting with meaningful messages
* Handling of incorrect number of arguments
* Enhance Max, Min, Add, Subtract, Multiply, Divide to accept (and process) any number of arguments (eg, `max(a,b,c,d,e,f)`)
* Handle constants - eg, 'pi' (currently interpreted as an input)
* Allow sub-values to be used as inputs - eg, `dist=(x**2+y**2+z**2)**0.5,biggest=max(x,y,z),combined=dist*biggest`
* Allow sub-values to be hidden from the 'output' - eg, by prefixing name with `_`


ParticlesToPath
===============
Download
* Blender 2.79 : https://github.com/baldingwizard/Blender-Addons/raw/master/ParticlesToPath279.zip
* Blender 2.8 : https://github.com/baldingwizard/Blender-Addons/raw/master/ParticlesToPath28.zip
(Note : Blender 2.8 version has to currently be accessed via the operator (press F3 and type 'Particle...')

Adds an option ('Particles to Nurbs') to the Add/Curve menu in the 3D View to convert a Particle System on the currently selected object into a (NURBS) curve. By emitting particles from a single vertex and then converting to a curve the path will follow the path of that vertex. This can be used to generate 'trails' as in this BSE answer : https://blender.stackexchange.com/a/94976/29586