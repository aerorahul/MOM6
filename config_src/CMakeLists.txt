# solo_driver
list(APPEND _solo_files
  ${CMAKE_CURRENT_SOURCE_DIR}/solo_driver/atmos_ocean_fluxes.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/solo_driver/MESO_surface_forcing.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/solo_driver/MOM_surface_forcing.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/solo_driver/Neverland_surface_forcing.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/solo_driver/user_surface_forcing.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/solo_driver/MOM_driver.F90)

# ice_solo_driver
list(APPEND _ice_solo_files
  ${CMAKE_CURRENT_SOURCE_DIR}/ice_solo_driver/MOM_surface_forcing.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/ice_solo_driver/atmos_ocean_fluxes.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/ice_solo_driver/user_surface_forcing.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/ice_solo_driver/ice_shelf_driver.F90)

# nuopc_driver
list(APPEND _nuopc_files
  ${CMAKE_CURRENT_SOURCE_DIR}/nuopc_driver/mom_cap.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/nuopc_driver/mom_cap_methods.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/nuopc_driver/mom_cap_time.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/nuopc_driver/mom_ocean_model_nuopc.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/nuopc_driver/mom_surface_forcing_nuopc.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/nuopc_driver/ocn_comp_NUOPC.F90
  ${CMAKE_CURRENT_SOURCE_DIR}/nuopc_driver/time_utils.F90)

# Send these files upstream as mom6_<application>_files
set(mom6_solo_files ${_solo_files} PARENT_SCOPE)
set(mom6_ice_solo_files ${_ice_solo_files} PARENT_SCOPE)
set(mom6_nuopc_files ${_nuopc_files} PARENT_SCOPE)
