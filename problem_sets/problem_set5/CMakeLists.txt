cmake_minimum_required(VERSION 3.28)
project(histogram)
enable_language(CUDA)

file( GLOB  hdr *.hpp *.h )

SET (HW5_files main.cu student.cu reference_calc.cpp)

ADD_EXECUTABLE(HW5 ${HW5_files} ${hdr})