# OpenGL_NinjaStar

OpenGL window and simple drawing with Visual C++.  

## Tasks

+ Using OpenGL, create a window.
+ Implement display function to draw the requirements below.
+ Draw a gray colored ninja star lying on a yellow background. The end result is supposed to look like the figure below.  

![ninja star drawing](https://github.com/iremozkal/OpenGL_NinjaStar/blob/main/Images/img1.PNG?raw=true)

+ Measurements and ratios of your star should conform to the template given below. 
 
![ninja star measurements](https://github.com/iremozkal/OpenGL_NinjaStar/blob/main/Images/img2.PNG?raw=true)

**NOTE**: Implement your homework using OpenGL 3.1 version or higher. All programming assignments must use the shader-based functionality of OpenGL: 1) no immediate mode 2) at least one vertex shader and one fragment shader. Therefore, you should not use any of the deprecated features of the API, e.g. glBegin, glEnd, glVertex3f, glTranslate etc.  


## Solution
+ On a yellow background; a gray square from triangles for the center area, four gray triangles for star edges, five yellow circles are required for my solution to draw this figure.  
+ For triangles, basically I set the vertices and colors and used GL_TRIANGLE_FAN to draw them.  
+ To draw circles; created a function that uses for loop to draw these five circles. I decided to draw all of them at once, not to call init() function five times more to draw each circle. In initialization function, six vertex array objects and two buffer objects are used. One vao is for triangles and the rests are for the five circles. I have float arrays to keep the vertex and color information of the circles.  

```bash
   x = radius * cos(i * 4.0f * M_PI / numberOfSlides);
   y = radius * sin(i * 4.0f * M_PI / numberOfSlides);
```
+ These equations are used for generating x,y coordinates of a circle. And the
array that has the circle points has these coordinates according to radius. To display it, again GL_TRIANGLE_FAN is used but now with assuming like 360 vertices because of a full turn for a circle.

