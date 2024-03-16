# QtProtobuf Bug
This repository contains the code to reproduce [QTBUG-123400](https://bugreports.qt.io/browse/QTBUG-123400).

## Dependencies
You need the following dependencies installed on your system:
- Qt 6.6.1
  - Qt Protobuf
- Protobuf

Protobuf may also be installed with vcpkg as described in https://doc.qt.io/qt-6/protobuf.html. 

## Building
Include the Qt and Protobuf path when building from the command line:
```
cmake -B build/ -DCMAKE_PREFIX_PATH="C:\Qt\6.6.1\msvc2019_64;D:\vcpkg\packages\protobuf_x64-windows"
```
