cmake_minimum_required(VERSION 3.17)
project(momentum)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS "-D__STDC_CONSTANT_MACROS")

find_library(SWRESAMPLE_LIBRARY swresample)
find_library(SWSCALE_LIBRARY swscale)
find_library(AVCODEC_LIBRARY avcodec)
find_library(AVFORMAT_LIBRARY avformat)
find_library(AVUTIL_LIBRARY avutil)
find_library(AVDEVICE_LIBRARY avdevice)

add_executable(momentum main.cpp)

target_link_libraries(momentum PRIVATE ${SWRESAMPLE_LIBRARY})
target_link_libraries(momentum PRIVATE ${SWSCALE_LIBRARY})
target_link_libraries(momentum PRIVATE ${AVCODEC_LIBRARY}) 
target_link_libraries(momentum PRIVATE ${AVFORMAT_LIBRARY}) 
target_link_libraries(momentum PRIVATE ${AVUTIL_LIBRARY}) 
target_link_libraries(momentum PRIVATE ${AVDEVICE_LIBRARY}) 
