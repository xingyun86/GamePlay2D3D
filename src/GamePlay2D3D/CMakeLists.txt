cmake_minimum_required(VERSION 2.8)

project(GamePlay)

set(GAMEPLAY_VERSION 3.0.0)

set(CMAKE_CXX_STANDARD "11")
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# debug
message( "CMAKE_BUILD_TYPE: ${CMAKE_BUILD_TYPE}" )
if ( "${CMAKE_BUILD_TYPE}" STREQUAL "DEBUG" )
    add_definitions(-D_DEBUG)
endif()

# architecture
if ( CMAKE_SIZEOF_VOID_P EQUAL 8 )
set(ARCH_DIR "x64")
else()
set(ARCH_DIR "x86")
endif()

# gameplay vendor library
add_subdirectory(vendor)

# gameplay library
add_subdirectory(gameplay)

# gameplay samples
add_subdirectory(samples)

# gameplay encoder
# A pre-compiled executable can be found in 'gameplay/bin'. Uncomment to build yourself.
#add_subdirectory(tools/encoder)
#add_subdirectory(tools/luagen)
