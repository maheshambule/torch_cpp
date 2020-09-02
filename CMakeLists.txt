cmake_minimum_required(VERSION 3.0 FATAL_ERROR)
project(custom_ops)

list(APPEND CMAKE_PREFIX_PATH, "/Users/demo/.pyenv/versions/3.6.9/lib/python3.6/site-packages/torch/")
#find_package(Torch REQUIRED)

add_executable(example-app example.cpp)
target_link_libraries(example-app "${TORCH_LIBRARIES}")
set_property(TARGET example-app PROPERTY CXX_STANDARD 14)