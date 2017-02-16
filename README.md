# OpenCV demonstrator (GUI)

![OpenCV demonstrator (GUI)](screenshots/screenshot-opencv-demonstrator.png "OpenCV demonstrator (GUI)")


## Introduction

This open source **OpenCV demonstrator (GUI)**, originally developped by
[TSD Conseil](http://www.tsdconseil.fr), is now through this GitHub
repository opened to user contributions. With the help of the OpenCV
community we can make a very exciting product!

Screenshots and stable binary releases are available on the
[official OpenCV demonstrator web page](http://www.tsdconseil.fr/log/opencv/demo/index-en.html).

The project is written in C++. The following open source libraries are used:

- [OpenCV 3.0](http://opencv.org/) - a real-time computer vision library
- [gtkmm 3](http://www.gtkmm.org/en/) library for the GUI part
- [pugixml](http://pugixml.org/) for XML parsing


## Build from source

#Prereqs
sudo apt-get install build-essential cmake git pkg-config libjpeg8-dev libtiff4-dev libjasper-dev libpng12-dev libavcodec-dev libavformat-dev     
libswscale-dev libv4l-dev libgtk2.0-dev libatlas-base-dev gfortran libgtkmm-3.0-1 libgtkmm-3.0-dev libgtkmm-3.0-doc

#openCV
1. git clone [OpenCV 3.0](https://github.com/asaggi/opencv.git)
2. git clone [openCV-contrib](https://github.com/opencv/opencv_contrib.git)
2. cd opencv
3. mkdir build
4. cd build
5. cmake \
	-DCMAKE_BUILD_TYPE=RELEASE \
	-DCMAKE_INSTALL_PREFIX=~/usr/local \
	-DINSTALL_C_EXAMPLES=ON \
	-DOPENCV_EXTRA_MODULES_PATH=~/opencv_contrib/modules \
	-DBUILD_EXAMPLES=ON \
	-DBUILD_SHARED_LIBS=ON \
	-DWITH_GTK=ON  ../ 

6. make --jobs=4
7. sudo make install
8. sudo ldconfig

#opencv-demonstrator

1. export OCVIPATH="~/usr/local/include"
2. export OCVLPATH="~/usr/local/lib"
3. git clone [openCV-demonstrator](https://github.com/asaggi/opencv-demonstrator-1.git)
4. cd opencv-demonstrator
5. make linux


##Running

1. cd opencv-demonstrator/ocvdemo
2. ./build/debug/ocvdemo.exe


## License

The software is provided according to the GNU Lesser General Public License
(LGPL) version 3. Please see [LICENSE](LICENSE).
