cmake_minimum_required(VERSION 3.28)
project(hdr)
enable_language(CUDA)

FIND_PACKAGE( OpenCV REQUIRED )
INCLUDE_DIRECTORIES( "/usr/include/opencv4" )

SET (compare_files compare.cpp)
file( GLOB  hdr *.hpp *.h )
file( GLOB  cu  *.cu)
SET (HW3_files main.cpp loadSaveImage.cpp reference_calc.cpp compare.cpp)

ADD_EXECUTABLE(HW3 ${HW3_files} ${hdr} ${cu})

TARGET_LINK_LIBRARIES (HW3 -lopencv_core -lopencv_imgproc -lopencv_highgui -lopencv_imgcodecs)
