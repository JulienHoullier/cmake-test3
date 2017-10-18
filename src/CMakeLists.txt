# set up the source files compilation

# add the source files
set(SRC prog.cpp)

# define the executable in terms of the source files
add_executable(${EXE} ${SRC})

# add the needed libraries and special compiler flags
set_target_properties(${EXE} PROPERTIES 
			     COMPILE_FLAGS "${MPI_CXX_COMPILE_FLAGS}" 
			     LINK_FLAGS "${MPI_CXX_LINK_FLAGS}")

#include_directories(${MPI_CXX_INCLUDE_PATH})
target_link_libraries(${EXE} ${MPI_CXX_LIBRARIES})

# how to install this executable
install(TARGETS ${EXE} RUNTIME DESTINATION ${CMAKE_SOURCE_DIR}/bin)
