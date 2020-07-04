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

if(MOM6SOLO)
  message(STATUS "Building MOM6 ocean-only application")
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

### Build MOM6 library
set(libName ${PROJECT_NAME})
set(moduleDir "${CMAKE_CURRENT_BINARY_DIR}/include/${PROJECT_NAME}")

add_library(${libName} STATIC ${mom6_src_files})
add_library(${PROJECT_NAME}::${libName} ALIAS ${libName})

set_target_properties(${libName} PROPERTIES Fortran_MODULE_DIRECTORY
                                            ${moduleDir})

target_link_libraries(${libName} PUBLIC gsw::gsw_static
                                        fms::fms_8
                                        NetCDF::NetCDF_Fortran)

target_include_directories(${libName} PUBLIC
  $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/config_src/dynamic>
  $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/src/framework>)

target_include_directories(${libName} INTERFACE
  $<BUILD_INTERFACE:${moduleDir}>
  $<INSTALL_INTERFACE:include/${PROJECT_NAME}>)

if(OpenMP_Fortran_FOUND)
  target_link_libraries(${libName} PUBLIC OpenMP::OpenMP_Fortran)
endif()

# Install compiled Fortran modules
install(DIRECTORY ${moduleDir} DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})

# Install libmom6.a
install(
  TARGETS ${libName}
  EXPORT ${PROJECT_NAME}Exports
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib
  COMPONENT Library)

### Build MOM6 applications

if(MOM6SOLO)
  set(exeName "mom6solo.x")
  add_executable(${exeName} ${mom6_solo_files})
  add_dependencies(${exeName} mom6::mom6)
  target_link_libraries(${exeName} PUBLIC mom6::mom6)
  list(APPEND EXE_TARGETS ${exeName})
endif()

# Install mom6 applications
if(EXE_TARGETS)
  install(
    TARGETS ${EXE_TARGETS}
    RUNTIME DESTINATION bin
    COMPONENT Applications)
endif()

### Package config
include(CMakePackageConfigHelpers)
set(CONFIG_INSTALL_DESTINATION lib/cmake/${PROJECT_NAME})

export(EXPORT ${PROJECT_NAME}Exports
  NAMESPACE ${PROJECT_NAME}::
  FILE ${PROJECT_NAME}-targets.cmake)

configure_package_config_file(
  ${PROJECT_SOURCE_DIR}/cmake/MOM6Config.cmake.in ${CMAKE_BINARY_DIR}/${PROJECT_NAME}-config.cmake
  INSTALL_DESTINATION ${CONFIG_INSTALL_DESTINATION})
install(FILES ${CMAKE_BINARY_DIR}/${PROJECT_NAME}-config.cmake
  DESTINATION ${CONFIG_INSTALL_DESTINATION})

write_basic_package_version_file(
  ${CMAKE_BINARY_DIR}/${PROJECT_NAME}-config-version.cmake
  VERSION ${PROJECT_VERSION}
  COMPATIBILITY AnyNewerVersion)
install(FILES ${CMAKE_BINARY_DIR}/${PROJECT_NAME}-config-version.cmake
  DESTINATION ${CONFIG_INSTALL_DESTINATION})

install(EXPORT ${PROJECT_NAME}Exports
  NAMESPACE ${PROJECT_NAME}::
  FILE ${PROJECT_NAME}-targets.cmake
  DESTINATION ${CONFIG_INSTALL_DESTINATION})
