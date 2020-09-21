
#  WebGL Fundamentals
 WebGL is just a rasterization engine. It draws points, lines, and triangles based on code you supply. Getting WebGL to do anything else is up to you to provide code to use points, lines, and triangles to accomplish your task.
## Intro
WebGL runs on the GPU on your computer. As such you need to provide the code that runs on that GPU. You provide that code in the form of pairs of functions. Those 2 functions are called a **vertex shader** and a **fragment shader** and they are each written in a very strictly typed C/C++ like language called [GLSL](https://webglfundamentals.org/webgl/lessons/webgl-shaders-and-glsl.html).

WebGL only cares about 2 things: clip space coordinates and colors. Your job as a programmer using WebGL is to provide WebGL with those 2 things. You provide your 2 "shaders" to do this. A Vertex shader which provides the clip space coordinates and a fragment shader that provides the color.
### Vertex shader
A vertex shader's job is to compute vertex positions. Based on the positions the function outputs WebGL can then rasterize various kinds of primitives including points, lines, or triangles. 

### Fragment shader
A fragment shader's job is to compute a color for each pixel of the primitive currently being drawn.

### Drawing
Nearly all of the entire WebGL API is about setting up state for these pairs of functions to run. For each thing you want to draw you setup a bunch of state then execute a pair of functions by calling  `gl.drawArrays`  or  `gl.drawElements`  which executes your shaders on the GPU.

Any data you want those functions to have access to must be provided to the GPU. There are 4 ways a shader can receive data.
- attributes and buffers
- uniforms
- textures
- varyings

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTkwMjc2Mzc4NF19
-->