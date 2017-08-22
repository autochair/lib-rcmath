cmake_minimum_required(VERSION 2.8.3)
project(rcmath)

find_package(catkin REQUIRED COMPONENTS)

catkin_package(
	INCLUDE_DIRS include
	LIBRARIES rcmath
)


include_directories(include)
add_library(serial
	    src/rcmath/rc_linear_algebra.c
        src/rcmath/rc_linear_filter.c
        src/rcmath/rc_linear_matrix.c
        src/rcmath/rc_linear_neon_functions.c
        src/rcmath/rc_polynomial.c
        src/rcmath/rc_ring_buffer.c
        src/rcmath/rc_vector.c
        src/rcmath/rc_quaternion.c
        )



