cmake_minimum_required(VERSION 3.10)

# Add the NMEA2000 directory to include directories
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../NMEA2000/src)


# Create a library from the source files
add_library(NMEA2000_socketCAN STATIC
    NMEA2000_SocketCAN.cpp
    NMEA2000_SocketCAN.h
)

# Specify include directories
target_include_directories(NMEA2000_socketCAN PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/../NMEA2000/src
)

# Link with the nmea2000 library
target_link_libraries(NMEA2000_socketCAN PRIVATE nmea2000)