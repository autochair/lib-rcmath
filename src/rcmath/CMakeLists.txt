cmake_minimum_required(VERSION 2.8.3)
project(rcmath)

find_package(catkin REQUIRED COMPONENTS)

catkin_package(
	INCLUDE_DIRS include
	LIBRARIES rcmath
)


include_directories(include)
add_library(rcmath
	    src/rcmath/rc_linear_algebra.c
        src/rcmath/rc_filter.c
        src/rcmath/rc_matrix.c
        src/rcmath/rc_neon_functions.c
        src/rcmath/rc_polynomial.c
        src/rcmath/rc_ring_buffer.c
        src/rcmath/rc_vector.c
        src/rcmath/rc_quaternion.c
        )

install(DIRECTORY include/${PROJECT_NAME}/ DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION} FILES_MATCHING PATTERN "*.h" )
install(DIRECTORY include/${PROJECT_NAME}/ DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION} FILES_MATCHING PATTERN "*.hpp" )

install(TARGETS rcmath
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION})


