WebGLVolumeRendering
====================
Performs Volumetric Rendering and Slicing of Volumetric Data.
Capable of accepting 2D textures as input for densities.
For textures to work, running the code on server (could be localhost) is necessary.

For moving the eye around the grid, uncomment the corresponding code in animate() function
If the renderer is needed, then comment
#define SLICER
line in Fragment Shader.

If slicer is needed, then uncomment
#define SLICER
line in Fragment Shader.
To move the slice plane position along z axis, press 'w' to move towards positive z, and 's' to move towards negative z
You can also use 'a' and 'd' for the same functionality. But it will cause 2 images belonging to different 
depth planes to be visible simultaneously at different heights. It is good for comparing different depth plane
slices.

If you want to generate densities procedurally in renderer, then uncomment the line
den += (getSphereDensity(l, vec3(SPHERE_CENTER), SPHERE_RADIUS) / (delt / STEP));
and comment out the line
den += (getDensity(vec3(floor(l))));
in findQ() function
AND
in rayCast()function uncomment line:
float density = getSphereDensity(ray, vec3(SPHERE_CENTER), SPHERE_RADIUS);
and comment out:
float density = getDensity(vec3(floor(ray)));

You can also use 1 or 2 light sources by commenting and uncommenting the findQ() function calls in rayCast()
