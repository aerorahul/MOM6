list(APPEND libsrc_files
ALE/coord_adapt.F90
ALE/coord_hycom.F90
ALE/coord_rho.F90
ALE/coord_sigma.F90
ALE/coord_slight.F90
ALE/coord_zlike.F90
ALE/MOM_ALE.F90
ALE/MOM_regridding.F90
ALE/MOM_remapping.F90
ALE/P1M_functions.F90
ALE/P3M_functions.F90
ALE/PCM_functions.F90
ALE/PLM_functions.F90
ALE/polynomial_functions.F90
ALE/PPM_functions.F90
ALE/PQM_functions.F90
ALE/regrid_consts.F90
ALE/regrid_edge_values.F90
ALE/regrid_interp.F90
ALE/regrid_solvers.F90
core/MOM.F90
core/MOM_barotropic.F90
core/MOM_boundary_update.F90
core/MOM_checksum_packages.F90
core/MOM_continuity.F90
core/MOM_continuity_PPM.F90
core/MOM_CoriolisAdv.F90
core/MOM_dynamics_split_RK2.F90
core/MOM_dynamics_unsplit.F90
core/MOM_dynamics_unsplit_RK2.F90
core/MOM_forcing_type.F90
core/MOM_grid.F90
core/MOM_interface_heights.F90
core/MOM_isopycnal_slopes.F90
core/MOM_open_boundary.F90
core/MOM_PressureForce.F90
core/MOM_PressureForce_analytic_FV.F90
core/MOM_PressureForce_Montgomery.F90
core/MOM_transcribe_grid.F90
core/MOM_unit_tests.F90
core/MOM_variables.F90
core/MOM_verticalGrid.F90
diagnostics/MOM_debugging.F90
diagnostics/MOM_diagnostics.F90
diagnostics/MOM_obsolete_diagnostics.F90
diagnostics/MOM_obsolete_params.F90
diagnostics/MOM_PointAccel.F90
diagnostics/MOM_sum_output.F90
diagnostics/MOM_wave_speed.F90
diagnostics/MOM_wave_structure.F90
equation_of_state/MOM_EOS.F90
equation_of_state/MOM_EOS_linear.F90
equation_of_state/MOM_EOS_NEMO.F90
equation_of_state/MOM_EOS_TEOS10.F90
equation_of_state/MOM_EOS_UNESCO.F90
equation_of_state/MOM_EOS_Wright.F90
equation_of_state/MOM_TFreeze.F90
framework/MOM_random.F90
framework/MOM_array_transform.F90
framework/MOM_checksums.F90
framework/MOM_coms.F90
framework/MOM_constants.F90
framework/MOM_cpu_clock.F90
framework/MOM_diag_manager_wrapper.F90
framework/MOM_diag_mediator.F90
framework/MOM_diag_remap.F90
framework/MOM_diag_vkernels.F90
framework/MOM_document.F90
framework/MOM_domains.F90
framework/MOM_dyn_horgrid.F90
framework/MOM_error_handler.F90
framework/MOM_file_parser.F90
framework/MOM_get_input.F90
framework/MOM_hor_index.F90
framework/MOM_horizontal_regridding.F90
framework/MOM_intrinsic_functions.F90
framework/MOM_io.F90
framework/MOM_memory_macros.h
framework/MOM_restart.F90
framework/MOM_safe_alloc.F90
framework/MOM_spatial_means.F90
framework/MOM_unit_scaling.F90
framework/MOM_string_functions.F90
framework/MOM_time_manager.F90
framework/MOM_write_cputime.F90
framework/MOM_memory_macros.h
framework/version_variable.h
framework/MOM_transform_FMS.F90
ice_shelf/MOM_ice_shelf.F90
ice_shelf/MOM_ice_shelf_dynamics.F90
ice_shelf/MOM_ice_shelf_initialize.F90
ice_shelf/MOM_ice_shelf_state.F90
ice_shelf/MOM_marine_ice.F90
ice_shelf/user_shelf_init.F90
initialization/MOM_coord_initialization.F90
initialization/MOM_fixed_initialization.F90
initialization/MOM_grid_initialize.F90
initialization/MOM_shared_initialization.F90
initialization/MOM_state_initialization.F90
initialization/MOM_tracer_initialization_from_Z.F90
ocean_data_assim/MOM_oda_driver.F90
parameterizations/lateral/MOM_hor_visc.F90
parameterizations/lateral/MOM_internal_tides.F90
parameterizations/lateral/MOM_lateral_mixing_coeffs.F90
parameterizations/lateral/MOM_MEKE.F90
parameterizations/lateral/MOM_MEKE_types.F90
parameterizations/lateral/MOM_mixed_layer_restrat.F90
parameterizations/lateral/MOM_thickness_diffuse.F90
parameterizations/lateral/MOM_tidal_forcing.F90
parameterizations/vertical/MOM_ALE_sponge.F90
parameterizations/vertical/MOM_bkgnd_mixing.F90
parameterizations/vertical/MOM_bulk_mixed_layer.F90
parameterizations/vertical/MOM_CVMix_conv.F90
parameterizations/vertical/MOM_CVMix_ddiff.F90
parameterizations/vertical/MOM_CVMix_KPP.F90
parameterizations/vertical/MOM_CVMix_shear.F90
parameterizations/vertical/MOM_diabatic_aux.F90
parameterizations/vertical/MOM_diabatic_driver.F90
parameterizations/vertical/MOM_diapyc_energy_req.F90
parameterizations/vertical/MOM_energetic_PBL.F90
parameterizations/vertical/MOM_entrain_diffusive.F90
parameterizations/vertical/MOM_full_convection.F90
parameterizations/vertical/MOM_geothermal.F90
parameterizations/vertical/MOM_internal_tide_input.F90
parameterizations/vertical/MOM_kappa_shear.F90
parameterizations/vertical/MOM_opacity.F90
parameterizations/vertical/MOM_regularize_layers.F90
parameterizations/vertical/MOM_set_diffusivity.F90
parameterizations/vertical/MOM_set_viscosity.F90
parameterizations/vertical/MOM_sponge.F90
parameterizations/vertical/MOM_tidal_mixing.F90
parameterizations/vertical/MOM_vert_friction.F90
tracer/advection_test_tracer.F90
tracer/boundary_impulse_tracer.F90
tracer/DOME_tracer.F90
tracer/dye_example.F90
tracer/dyed_obc_tracer.F90
tracer/ideal_age_example.F90
tracer/ISOMIP_tracer.F90
tracer/MOM_generic_tracer.F90
tracer/MOM_neutral_diffusion.F90
tracer/MOM_OCMIP2_CFC.F90
tracer/MOM_offline_aux.F90
tracer/MOM_offline_main.F90
tracer/MOM_tracer_advect.F90
tracer/MOM_tracer_diabatic.F90
tracer/MOM_tracer_flow_control.F90
tracer/MOM_tracer_hor_diff.F90
tracer/MOM_tracer_registry.F90
tracer/RGC_tracer.F90
tracer/MOM_tracer_Z_init.F90
tracer/oil_tracer.F90
tracer/pseudo_salt_tracer.F90
tracer/tracer_example.F90
tracer/MOM_lateral_boundary_diffusion.F90
user/adjustment_initialization.F90
user/baroclinic_zone_initialization.F90
user/benchmark_initialization.F90
user/BFB_initialization.F90
user/BFB_surface_forcing.F90
user/circle_obcs_initialization.F90
user/dense_water_initialization.F90
user/DOME2d_initialization.F90
user/DOME_initialization.F90
user/dumbbell_initialization.F90
user/dumbbell_surface_forcing.F90
user/dyed_channel_initialization.F90
user/dyed_obcs_initialization.F90
user/external_gwave_initialization.F90
user/ISOMIP_initialization.F90
user/Idealized_Hurricane.F90
user/Kelvin_initialization.F90
user/lock_exchange_initialization.F90
user/MOM_controlled_forcing.F90
user/MOM_wave_interface.F90
user/Neverland_initialization.F90
user/Phillips_initialization.F90
user/RGC_initialization.F90
user/Rossby_front_2d_initialization.F90
user/SCM_CVMix_tests.F90
user/seamount_initialization.F90
user/shelfwave_initialization.F90
user/sloshing_initialization.F90
user/soliton_initialization.F90
user/supercritical_initialization.F90
user/tidal_bay_initialization.F90
user/user_change_diffusivity.F90
user/user_initialization.F90
user/user_revise_forcing.F90)

# CVMix
list(APPEND libsrc_files
parameterizations/CVmix/cvmix_background.F90
parameterizations/CVmix/cvmix_convection.F90
parameterizations/CVmix/cvmix_ddiff.F90
parameterizations/CVmix/cvmix_kinds_and_types.F90
parameterizations/CVmix/cvmix_kpp.F90
parameterizations/CVmix/cvmix_math.F90
parameterizations/CVmix/cvmix_put_get.F90
parameterizations/CVmix/cvmix_shear.F90
parameterizations/CVmix/cvmix_tidal.F90
parameterizations/CVmix/cvmix_utils.F90)

# MOM6-da-hooks
list(APPEND libsrc_files
ocean_data_assim/core/ocean_da_core.F90
ocean_data_assim/core/ocean_da_types.F90
ocean_data_assim/core/write_ocean_obs.F90)

# geoKdTree
list(APPEND libsrc_files
ocean_data_assim/geoKdTree/kdtree.f90)

# Build MOM6 library
set(libName ${PROJECT_NAME})
set(moduleDir "${CMAKE_CURRENT_BINARY_DIR}/include")

add_library(${libName} STATIC ${libsrc_files})
add_library(${PROJECT_NAME}::${libName} ALIAS ${libName})

set_target_properties(${libName} PROPERTIES Fortran_MODULE_DIRECTORY
                                            ${moduleDir})

target_link_libraries(${libName} PUBLIC gsw::gsw_static
                                        fms::fms_8
                                        NetCDF::NetCDF_Fortran)

target_include_directories(${libName} PUBLIC
  $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/config_src/dynamic>
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/framework>)

target_include_directories(${libName} INTERFACE
  $<BUILD_INTERFACE:${moduleDir}>
  $<INSTALL_INTERFACE:include>)

if(OpenMP_Fortran_FOUND)
  target_link_libraries(${libName} PUBLIC OpenMP::OpenMP_Fortran)
endif()

install(DIRECTORY ${moduleDir} DESTINATION ${CMAKE_INSTALL_PREFIX})

install(
  TARGETS ${libName}
  EXPORT ${PROJECT_NAME}Exports
  RUNTIME DESTINATION bin
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib
  COMPONENT Library)

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
