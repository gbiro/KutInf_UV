cmake_minimum_required(VERSION 3.0.0)
project(app)


add_custom_target(data DEPENDS ${CMAKE_BINARY_DIR}/map.dat)