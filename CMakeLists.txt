cmake_minimum_required(VERSION 3.10)
project(part3)

set(CMAKE_CXX_STANDARD 17)

add_executable(read_fc_plus    
    code/part3/read_fc.cpp
    code/part3/scr/Matrix_template.cpp
    code/part3/scr/Model_template.cpp
)

target_include_directories(read_fc_plus PRIVATE code/part3/include)

find_package(nlohmann_json CONFIG REQUIRED)
target_link_libraries(read_fc_plus PRIVATE nlohmann_json::nlohmann_json)