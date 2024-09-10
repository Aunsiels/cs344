cmake_minimum_required(VERSION 3.28)
project(blackwhite)
enable_language(CUDA)

FIND_PACKAGE( OpenCV REQUIRED )
INCLUDE_DIRECTORIES( ${OpenCV_INCLUDE_DIRS} )

file( GLOB  hdr *.hpp *.h )
file( GLOB  cu  *.cu)
SET (HW1_files main.cpp reference_calc.cpp compare.cpp)

ADD_EXECUTABLE(HW1 ${HW1_files} ${hdr} ${cu})

TARGET_LINK_LIBRARIES (HW1 ${OpenCV_LIBS})
