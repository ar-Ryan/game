cmake_minimum_required(VERSION 3.10)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(hello VERSION 1.0)

# Find SDL2 package
find_package(SDL2 REQUIRED)

# Include SDL2 headers
include_directories(${SDL2_INCLUDE_DIRS})

# Locate the source files
file(GLOB SOURCES "src/*.cpp")

# Add the executable
add_executable(hello ${SOURCES})

# Link SDL2 libraries
target_link_libraries(hello ${SDL2_LIBRARIES})

# Include additional directories (if needed)
target_include_directories(hello PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)
