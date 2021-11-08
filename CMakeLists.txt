cmake_minimum_required(VERSION 3.20)
project(pytorch_cpp_example)

find_package(protobuf REQUIRED)
find_package(Torch REQUIRED)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${TORCH_CXX_FLAGS}")

message("TORCH_CXX_FLAGS are: ${TORCH_CXX_FLAGS}")
message("TORCH_LIBRARIES ${TORCH_LIBRARIES}")

include_directories("/usr/local/include/torch/csrc/api/include")
link_directories("third_party/libtorch/lib")

add_executable(pytorch_cpp_example main.cpp)
target_link_libraries(pytorch_cpp_example ${TORCH_LIBRARIES})
