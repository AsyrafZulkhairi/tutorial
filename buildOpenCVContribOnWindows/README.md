# How to build OpenCV with OpenCV contrib on Windows

## Install CMake and Download OpenCV Source

Download CMake installer from it's download page. Choose either 64-bit or 32-bit depends on your machine:

![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/buildOpenCVContribOnWindows/image/downloadCMakeInstaller.png "downloadCMakeInstaller.png")

Run the installer and during installation select “Add CMake to the system PATH for the current user”.

Download OpenCV and OpenCV Contrib source code zip. Download OpenCV source code zip from Github (you can choose which version):

![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/buildOpenCVContribOnWindows/image/downloadOpenCVSource.PNG "downloadOpenCVSource.PNG")

Then download OpenCV Contrib (make sure the same version as the chosen main OpenCV):

![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/buildOpenCVContribOnWindows/image/downloadOpenCVContribSource.PNG "downloadOpenCVContribSource.PNG")

Extract both zip files in a folder:

![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/buildOpenCVContribOnWindows/image/extractOpenCVSourceZip.PNG "extractOpenCVSourceZip.PNG")

## Build OpenCV with OpenCV contrib

Run CMake, set "Where is the source code:" to path of the OpenCV (the path should contain 3rdparty, apps, modules folder).  
Then set "Where to build the binaries:" with same path but add '/build' at the end (this will create build directory):  
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/buildOpenCVContribOnWindows/image/cmakeSetDirectory.PNG "cmakeSetDirectory.PNG")

Click 'Configure', select your prefered compiler:  
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/buildOpenCVContribOnWindows/image/cmakeSetGenerator.PNG "cmakeSetGenerator.PNG")

Then click 'Finish'.  
Check "INSTALL_C_EXAMPLES" and "INSTALL_PYTHON_EXAMPLES".  
In flag "OPENCV_EXTRA_MODULES_PATH", set the path to 'modules' folder in OpenCV contrib:  
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/buildOpenCVContribOnWindows/image/cmakeSetContribModulePath.PNG "cmakeSetContribModulePath.PNG")

Then click 'configure' (everytime after make values changes, click 'configure').  
After "Configuring done." and no errors, click 'Generate'.  
Finish and now ready to build OpenCV. Open command line in 'build' folder in OpenCV path.  
An easy way to do that, go to the build folder in Windows Explorer, type 'cmd' in address bar then press Enter:  
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/buildOpenCVContribOnWindows/image/buildFolderCmd.png "buildFolderCmd.png")

Then in cmd, use following command:  
Debug Mode: `cmake.exe --build . --config Debug --target INSTALL`  
Release Mode: `cmake.exe --build . --config Release --target INSTALL`  
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/buildOpenCVContribOnWindows/image/buildInCmd.PNG "buildInCmd.PNG")

Which mode depends on your project. For example in Visual Studio that using Debug mode, you need to build Debug mode:  
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/buildOpenCVContribOnWindows/image/VSDebugMode.png "VSDebugMode.png")

`--config Debug` will create .lib with 'd' at the end of name, `--config Release` create normal .lib files:  
![alt text](https://github.com/AsyrafZulkhairi/tutorial/blob/master/buildOpenCVContribOnWindows/image/openCVDebugLib.PNG "openCVDebugLib.PNG")

## Reference
https://www.learnopencv.com/install-opencv3-on-windows/

