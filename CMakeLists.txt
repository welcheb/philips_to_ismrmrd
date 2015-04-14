cmake_minimum_required(VERSION 2.6)

project(SIEMENS-TO-ISMRMRD)

#VERSIONING
set(PHILIPS_TO_ISMRMRD_VERSION_MAJOR 0)
set(PHILIPS_TO_ISMRMRD_VERSION_MINOR 0)
set(PHILIPS_TO_ISMRMRD_VERSION_PATCH 1)
set(PHILIPS_TO_ISMRMRD_VERSION_STRING ${PHILIPS_TO_ISMRMRD_VERSION_MAJOR}.${PHILIPS_TO_ISMRMRD_VERSION_MINOR}.${PHILIPS_TO_ISMRMRD_VERSION_PATCH})

if (WIN32)
    ADD_DEFINITIONS(-DWIN32 -D_WIN32 -D_WINDOWS)
    # ADD_DEFINITIONS(-DUNICODE -D_UNICODE)
    SET (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /EHsc /MP")
    SET (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /W3")
    SET (CMAKE_EXE_LINKER_FLAGS_DEBUG "/debug /INCREMENTAL:NO")
    SET (CMAKE_SHARED_LINKER_FLAGS_DEBUG "/debug /INCREMENTAL:NO")
    SET (CMAKE_STATIC_LINKER_FLAGS_DEBUG "/debug /INCREMENTAL:NO")
    SET (CMAKE_MODULE_LINKER_FLAGS_DEBUG "/debug /INCREMENTAL:NO")

    #ADD_DEFINITIONS(-D__BUILD_CONVERTER_TINYXML__)
endif (WIN32)

#find_package(Ismrmrd REQUIRED)

INCLUDE_DIRECTORIES( ${ISMRMRD_INCLUDE_DIR} )

add_executable(philips_to_ismrmrd 
               main.cpp) 