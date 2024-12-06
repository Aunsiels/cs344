cmake_minimum_required(VERSION 3.28)
project(blending)
enable_language(CUDA)

FIND_PACKAGE( OpenCV REQUIRED )
INCLUDE_DIRECTORIES( "/usr/include/opencv4" )

file( GLOB  hdr *.hpp *.h )
SET (HW6_files student_func.cu HW6.cu main.cpp loadSaveImage.cpp reference_calc.cpp compare.cpp)

ADD_EXECUTABLE(HW6 ${HW6_files} ${hdr})

TARGET_LINK_LIBRARIES (HW6 -lopencv_core -lopencv_imgproc -lopencv_highgui -lopencv_imgcodecs)
