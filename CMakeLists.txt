cmake_minimum_required(VERSION 3.9)
project (Signals)

add_executable(Signals 
	main.cpp
	signals.hpp
	Bench.h
)
set_target_properties(Signals PROPERTIES
	CXX_STANDARD 17
	CXX_STANDARD_REQUIRED ON
	CXX_EXTENSIONS OFF
)

# Create header-only library target
add_library(fteng-signals INTERFACE)
target_include_directories(fteng-signals INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    $<INSTALL_INTERFACE:include>
)
