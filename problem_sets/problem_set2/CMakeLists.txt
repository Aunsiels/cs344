cmake_minimum_required(VERSION 3.28)
project(blur)
enable_language(CUDA)

FIND_PACKAGE( OpenCV REQUIRED )
INCLUDE_DIRECTORIES( "/usr/include/opencv4" )

file( GLOB  hdr *.hpp *.h )
file( GLOB  cu  *.cu)
SET (HW2_files main.cpp reference_calc.cpp compare.cpp)

ADD_EXECUTABLE(HW2 ${HW2_files} ${hdr} ${cu})

TARGET_LINK_LIBRARIES (HW2 -lopencv_core -lopencv_imgproc -lopencv_highgui -lopencv_imgcodecs)
