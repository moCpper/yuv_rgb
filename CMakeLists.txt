cmake_minimum_required(VERSION 3.10)
project(yuvDemo-cpp)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/build/bin)

find_package(Qt5 COMPONENTS Core Widgets REQUIRED)
find_package(FFMPEG REQUIRED)
find_package(SDL2 REQUIRED)

file(GLOB SOURCES "src/*.cpp")

add_executable(yuvDemo-cpp ${SOURCES})

target_link_libraries(yuvDemo-cpp Qt5::Core Qt5::Widgets ${FFMPEG_LIBRARIES} SDL2::SDL2)

target_include_directories(yuvDemo-cpp PRIVATE 
    ${PROJECT_SOURCE_DIR}/include 
    ${FFMPEG_INCLUDE_DIRS} 
    ${SDL2_INCLUDE_DIRS}
)
