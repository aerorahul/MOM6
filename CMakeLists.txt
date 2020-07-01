cmake_minimum_required(VERSION 3.15)

project(
  mom6
  VERSION 2020.07.01
  LANGUAGES Fortran)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

include(GNUInstallDirs)

# Compilation options
option(OPENMP "Enable OpenMP threading" OFF)

# Application options
option(MOM6SOLO "Build MOM6 ocean-only application" ON)
option(MOM6SIS2 "Build MOM6 + SIS2 application" OFF)

if(MOM6SOLO)
  message(STATUS "Building MOM6 ocean-only application")
endif()
if(MOM6SIS2)
  message(STATUS "Building MOM6 + SIS2 application")
endif()

if(NOT CMAKE_BUILD_TYPE MATCHES "^(Debug|Release|RelWithDebInfo|MinSizeRel)$")
  message(STATUS "Setting build type to 'Release' as none was specified.")
  set(CMAKE_BUILD_TYPE
      "Release"
      CACHE STRING "Choose the type of build." FORCE)
  set_property(CACHE CMAKE_BUILD_TYPE PROPERTY STRINGS "Debug" "Release"
                                               "MinSizeRel" "RelWithDebInfo")
endif()

if(NOT CMAKE_Fortran_COMPILER_ID MATCHES "^(Intel|GNU|Clang|AppleClang)$")
  message(WARNING "Compiler not officially supported: ${CMAKE_Fortran_COMPILER_ID}")
endif()

find_package(NetCDF REQUIRED COMPONENTS Fortran)
find_package(gsw REQUIRED COMPONENTS STATIC)
find_package(fms REQUIRED)

if(OPENMP)
  find_package(OpenMP REQUIRED COMPONENTS Fortran)
endif()

include(mom6_compiler_flags)

add_subdirectory(src)
add_subdirectory(config_src)
