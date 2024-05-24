cmake_minimum_required(VERSION 3.20.0)
project(raylib-test VERSION 0.1.0 LANGUAGES C CXX)
# Set the policy to use CMake package registry
cmake_policy(SET CMP0074 NEW)

# Set the CMake toolchain file for vcpkg
set(CMAKE_TOOLCHAIN_FILE "/Users/borisposavec/vcpkg/scripts/buildsystems/vcpkg.cmake")
message("[TOOLCHAIN] "  ${CMAKE_TOOLCHAIN_FILE})

find_package(spdlog CONFIG REQUIRED)
find_package(raylib CONFIG REQUIRED)

add_executable(raylib-test main.cpp)

target_link_libraries(
  ${PROJECT_NAME} 
  PRIVATE 
  spdlog::spdlog
  raylib
)

target_compile_features(
  ${PROJECT_NAME}
  PUBLIC
  cxx_std_20
)
