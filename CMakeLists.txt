cmake_minimum_required(VERSION 3.13)
project(i2cController)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)


add_library(I2C src/I2C.h src/I2C.cpp )

set_target_properties(I2C PROPERTIES OUTPUT_NAME "I2C")
install(TARGETS I2C DESTINATION "include")