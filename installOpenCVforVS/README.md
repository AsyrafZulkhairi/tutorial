# How to setup OpenCV for Visual Studio

## Installing OpenCV
Download OpenCV installer at OpenCV site. For example this tutorial use `OpenCV - 3.4.10`:
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/installOpenCVforVS/OpenCVDownloadPage.PNG "OpenCVDownloadPage.PNG")

Run the installer and select the path to extract. This tutorial use `C:\opencv_3.4.10`. After installation:
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/installOpenCVforVS/pathOpenCV.PNG "pathOpenCV.PNG")

Add OpenCV's `bin` directory to path. Go to `System Properties > Advanced > Environment Variables...`:
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/installOpenCVforVS/editEnvironmentVariables.PNG "editEnvironmentVariables.PNG")
Then edit 'Path':
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/installOpenCVforVS/editSystemVariables.png "editSystemVariables.png")
Add OpenCV's 'bin' directory. The path depends on extract path previously. For example:
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/installOpenCVforVS/addOpenCVPath.PNG "addOpenCVPath.PNG")



## Setting in Visual Studio
Open a project you want to add OpenCV, then go to project setting:
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/installOpenCVforVS/VSProjectProperties.PNG "VSProjectProperties.PNG")

Make sure `Configuration` and `Platform` is correct (depends on which one you use). For example `Configuration: Debug` and `Platform: x64` as in picture below.

Go to `Configuration Properties > VC++ Directories`, edit `Include Directories` and `Library Directories`:
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/installOpenCVforVS/VC++Directories.PNG "VC++Directories.PNG")
For `Include Directories`, use path of `opencv2`:
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/installOpenCVforVS/includePath.PNG "includePath.PNG")
For `Library Directories`, use path of `opencv_world3410d.lib`:
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/installOpenCVforVS/libPath.PNG "libPath.PNG")

Then go to `Configuration Properties > Linker > Input`, edit `Additional Dependencies` and add `opencv_world****d.lib` depending on your OpenCV, you can check at `\opencv\build\x64\vc15\lib`:
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/installOpenCVforVS/linkerInput.PNG "linkerInput.PNG")

That's it. Choose 'apply' to close.



## Testing
Done. To test, try type in your code `#include <open`, suggestions will pop-up indicates OpenCV is ready:
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/installOpenCVforVS/testOpenCVa.PNG "testOpenCVa.PNG")
Similarly, example of Visual Studio suggesting for `opencv2/core.hpp`:
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/installOpenCVforVS/testOpenCVb.PNG "testOpenCVb.PNG")
