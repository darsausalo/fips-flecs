#
# project: fips-flecs
#

if (NOT FIPS_IMPORT)
	project (flecs C)
	set(CMAKE_C_STANDARD 99)

	cmake_minimum_required(VERSION 2.8)
	get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
	include("${FIPS_ROOT_DIR}/cmake/fips.cmake")
	fips_setup()
	fips_project(fips-flecs)
endif()

fips_begin_lib(flecs)
	include_directories(flecs/include)
	fips_files_ex(flecs/src/ *.c)
	add_definitions(-Dflecs_STATIC)
fips_end_lib()

if (NOT FIPS_IMPORT)
	fips_finish()
endif()
