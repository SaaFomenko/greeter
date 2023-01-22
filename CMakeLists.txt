cmake_minimum_required(VERSION 3.5)

project(greeter)

file(GLOB
	lib_source "./lib/${PROJECT_NAME}_lib/*.cpp")

add_library(${PROJECT_NAME}_lib STATIC ${lib_source})

add_executable(${PROJECT_NAME}.exe main.cpp ${lib_source})

target_link_libraries(${PROJECT_NAME}.exe ${PROJECT_NAME}_lib)
