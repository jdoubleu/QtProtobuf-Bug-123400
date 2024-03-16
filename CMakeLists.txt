cmake_minimum_required(VERSION 3.14)
project(QtProtobufBug LANGUAGES CXX)

find_package(Qt6 REQUIRED COMPONENTS Core)

add_executable(QtProtobufBug main.cpp)
target_link_libraries(QtProtobufBug Qt6::Core)
