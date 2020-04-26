cmake_minimum_required (VERSION 3.15)
project(soloud)
if(POLICY CMP0079)
  cmake_policy(SET CMP0091 NEW)
endif()
if(POLICY CMP0079)
  cmake_policy(SET CMP0079 NEW)
endif()


file(GLOB_RECURSE SOLOUD_SOURCE 		"${CMAKE_CURRENT_SOURCE_DIR}/src/**.c*")

add_definitions()

add_library(soloud OBJECT 
	${SOLOUD_SOURCE}
	)





set_target_properties(soloud PROPERTIES FOLDER "Dependencies/soloud")
set_property(TARGET soloud PROPERTY MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>DLL")
