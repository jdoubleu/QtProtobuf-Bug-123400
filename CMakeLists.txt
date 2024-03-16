cmake_minimum_required(VERSION 3.14)
project(QtProtobufBug LANGUAGES CXX)

find_package(Protobuf REQUIRED)
find_package(Qt6 REQUIRED COMPONENTS Core Protobuf)

# QtProtobuf
qt_add_protobuf(ProtobufsQt
    PROTO_FILES "bug.proto")

# Vanilla protobuf
protobuf_generate_cpp(ProtobufsPlain_SRCS ProtobufsPlain_HDRS "bug.proto")
add_library(ProtobufsPlain STATIC ${ProtobufsPlain_SRCS} ${ProtobufsPlain_HDRS})
target_include_directories(ProtobufsPlain PUBLIC ${CMAKE_CURRENT_BINARY_DIR})
target_link_libraries(ProtobufsPlain PUBLIC protobuf::libprotobuf)

# app
add_executable(QtProtobufBug main.cpp)
target_link_libraries(QtProtobufBug Qt6::Core ProtobufsPlain ProtobufsQt)
