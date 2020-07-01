# solo_driver
list(APPEND _solo_files
  solo_driver/atmos_ocean_fluxes.F90
  solo_driver/MESO_surface_forcing.F90
  solo_driver/MOM_surface_forcing.F90
  solo_driver/Neverland_surface_forcing.F90
  solo_driver/user_surface_forcing.F90)
set(_solo_driver solo_driver/MOM_driver.F90)

if(MOM6SOLO)
  set(exeName "mom6solo.x")
  add_executable(${exeName} ${_solo_files} ${_solo_driver})
  add_dependencies(${exeName} mom6::mom6)
  target_link_libraries(${exeName} PUBLIC mom6::mom6)
  list(APPEND EXE_TARGETS ${exeName})
endif()

# ice_solo_driver
list(APPEND _ice_solo_files
  ice_solo_driver/MOM_surface_forcing.F90
  ice_solo_driver/atmos_ocean_fluxes.F90
  ice_solo_driver/user_surface_forcing.F90)
set(_ice_solo_driver ice_solo_driver/ice_shelf_driver.F90)

if(MOM6SIS2)
  set(exeName "mom6sis2.x")
  add_executable(${exeName} ${_ice_solo_files} ${_ice_solo_driver})
  add_dependencies(${exeName} mom6::mom6)
  target_link_libraries(${exeName} PUBLIC mom6::mom6)
  list(APPEND EXE_TARGETS ${exeName})
endif()

if(EXE_TARGETS)
  install(TARGETS ${EXE_TARGETS}
  RUNTIME DESTINATION bin COMPONENT Applications)
endif()
