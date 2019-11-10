cmake_minimum_required(VERSION 3.6)
add_definitions(-D__wiiu__)
set(CMAKE_TOOLCHAIN_FILE $ENV{WUT_ROOT}/share/wut.toolchain.cmake)

project(iosuhax)

include("$ENV{WUT_ROOT}/share/wut.cmake" REQUIRED)

include_directories($ENV{DEVKITPRO}/portlibs/ppc/include
        $ENV{DEVKITPRO}/portlibs/wiiu/include)
link_directories($ENV{DEVKITPRO}/portlibs/ppc/lib
        $ENV{DEVKITPRO}/portlibs/wiiu/lib)

include_directories(source)

set(SOURCE_FILES
	source/iosuhax.c
	source/iosuhax_devoptab.c
	source/iosuhax_disc_interface.c)
add_library(iosuhax STATIC ${SOURCE_FILES})