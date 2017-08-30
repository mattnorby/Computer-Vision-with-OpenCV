# Computer-Vision-with-OpenCV
Conference session - under construction

Session outline (draft)

intro - about myself
 
background about OpenCV
open source computer vision library
sample use cases
- detect/track colored ball (color spaces / HSV)
- detect faces (without recognizing them)
- high dynamic range (HDR) photographic color enhancement
- Aruco marker detection / augmented reality
- image stitching (panoramas, "twins" photos; stitching models spherical vs. cylindrical)
- seamless cloning
- video
 
OpenCV history
open source BSD license
created in 1999 by Intel Research
first public alpha in 2000
1.0 - 2006
1.1 - Oct 2008
2.0 - Oct 2009
(missing timeline for later releases)
 
supported platforms
desktop: Windows, Linux, macOS, FreeBSD, NetBSD, OpenBSD
mobile: Android, iOS, Maemo, BlackBerry 10
 
performance
- hardware acceleration via Intel's Integrated Performance Primitives (if available)
- CUDA-based GPU interface
- OpenCL-based GPU interface
 
language support
- C++ (OpenCV is written in C++)
- bindings in the library for Python, Java, MATLAB
- wrappers available for C#, Perl, Ch, Haskell, Ruby
 
getting started
http://opencv.org
libraries come precompiled for Visual Studio
for other tools, need a compiler (e.g. MinGW) and CMake (links to how to)
  CMake does not make the library, it makes the makefile
Get an IDE (e.g. Visual Studio for VC++, Code Blocks for MinGW)
Create a project, include headers, tell the linker what libraries you're using
OpenCV has their own tutorials, helpful for understanding usage, parameters

library structure - divided into modules
- core
- imgproc (image processing)
- highgui (high-level GUI and media)
- calib3d (camera calibration and 3D reconstruction)
- feature2d (2D features framework)
- video (video analysis)
- objdetect (object detection)
- ml (machine learning)
- photo (computational photography)
- gpu (hardware acceleration)
- viz (visualization tool)
 
look at a few sample library methods, explain what they do, how they are used
- thresholding, to reduce to black and white
  create a mask this way, to isolate something in the image
- "convolution" of a matrix
  erode, dilate, open, close to find contours, reduce noise, close holes
- color space conversion from RGB to HSV or YUV
  simplifies the search for specific hues (e.g. colored ball)
- detect lines, circles

demos
- track a colored ball
  (color space conversion to HSV, threshold a range of hues)
- detect faces
  (Haar classifiers built into the library)
- create your own twin
  (image stitching)
- insert 3D objects into video
  (augmented reality using Aruco markers)
 
common complications
- "noise" in image (because light is a wave, not so much because of camera quality)
  strategies: remove (filter, threshold), ignore (histogram)
- lighting (can affect color recognition, makes thresholding trickier)
  strategies: histogram equalization, more light, light oriented toward subject
- occlusions
- distortion from camera lens
  strategies: calibrate camera, call undistort method
 
when to think about other tools
- line following robot: look at Johnny Five
- large point clouds: look at Point Cloud Library (PCL)
  or... OpenCV contributor module "structure from motion"
