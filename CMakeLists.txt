cmake_minimum_required(VERSION 3.26)
project(onnxruntime_vendor)

find_package(ament_cmake REQUIRED)
find_package(ament_cmake_vendor_package REQUIRED)

find_package(onnxruntime QUIET)

ament_vendor(onnxruntime_vendor
  SATISFIED ${onnxruntime_FOUND}
  VCS_URL https://github.com/microsoft/onnxruntime.git
  VCS_VERSION v1.17.0
  SOURCE_SUBDIR cmake
  CMAKE_ARGS
    -Donnxruntime_BUILD_SHARED_LIB:BOOL=ON
    -DBUILD_SHARED_LIBS:BOOL=OFF
    -Donnxruntime_BUILD_UNIT_TESTS:BOOL=OFF
    -Donnxruntime_USE_FULL_PROTOBUF:BOOL=ON
)

ament_package()
