cmake_minimum_required(VERSION 3.28)
project(redeye)
enable_language(CUDA)

FIND_PACKAGE( OpenCV REQUIRED )
INCLUDE_DIRECTORIES( "/usr/include/opencv4" )

SET (compare_files compare.cpp)
file( GLOB  hdr *.hpp *.h )
file( GLOB  cu  *.cu)
SET (HW4_files main.cpp loadSaveImage.cpp reference_calc.cpp compare.cpp)

ADD_EXECUTABLE(HW4 ${HW4_files} ${hdr} ${img} ${cu})

TARGET_LINK_LIBRARIES (HW4 -lopencv_core -lopencv_imgproc -lopencv_highgui -lopencv_imgcodecs)
