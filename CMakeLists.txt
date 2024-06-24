cmake_minimum_required(VERSION 3.20)

set(vcpkg "$ENV{VCPKG_ROOT}/scripts/buildsystems/vcpkg.cmake")
if(NOT CMAKE_TOOLCHAIN_FILE AND EXISTS "${vcpkg}")
  set(CMAKE_TOOLCHAIN_FILE "${vcpkg}"
      CACHE FILEPATH "CMake toolchain file")
  message(STATUS "vcpkg toolchain found: ${CMAKE_TOOLCHAIN_FILE}")
endif()


set(CMAKE_CXX_VERSION 20)
set(CMAKE_CXX_VERSION_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

project(bin_tplt CXX)

find_package(fmt REQUIRED)
find_package(range-v3 REQUIRED)
find_package(cxxopts REQUIRED)

add_executable(bin_tplt src/main.cpp)

target_link_libraries(bin_tplt
  PRIVATE
    fmt::fmt
    range-v3::range-v3
    cxxopts::cxxopts  
)