cmake_minimum_required(VERSION 3.10)

project(Part6_ImageProcessing)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package(OpenCV REQUIRED)
find_package(nlohmann_json REQUIRED)

include_directories(
    ${OpenCV_INCLUDE_DIRS}
    ../code/part1/include
    ../code/part5/tcpSocket
)

set(CLIENT_SOURCES
    ../code/part6/normal.cpp
    ../code/part1/scr/Model.cpp
    ../code/part1/scr/Matrix.cpp
    ../code/part5/tcpSocket/tcpSocket.cpp
)

add_executable(Part6_ImageProcessing ${CLIENT_SOURCES})
target_link_libraries(Part6_ImageProcessing ${OpenCV_LIBS})
target_link_libraries(Part6_ImageProcessing nlohmann_json::nlohmann_json)

set(SERVER_SOURCES
    ../code/part5/Server.cpp
    ../code/part1/scr/Model.cpp
    ../code/part1/scr/Matrix.cpp
    ../code/part5/tcpSocket/tcpSocket.cpp
)

add_executable(Server ${SERVER_SOURCES})
target_link_libraries(Server ${OpenCV_LIBS})
target_link_libraries(Server nlohmann_json::nlohmann_json)

