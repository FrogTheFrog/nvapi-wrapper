#----------------------------------------------------------------------------------------------------------------------
# Cmake settings
#----------------------------------------------------------------------------------------------------------------------

cmake_minimum_required(VERSION 3.27)
project(nvapiwrapper
        DESCRIPTION "Custom C++ bindings for as an internal dependency for other projects"
        HOMEPAGE_URL "https://github.com/FrogTheFrog/nvapi-wrapper"
        LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

#----------------------------------------------------------------------------------------------------------------------
# Header files
#----------------------------------------------------------------------------------------------------------------------

set(HEADERS
    src/nvapidrssession.h
    src/nvapiwrapper.h
    )

#----------------------------------------------------------------------------------------------------------------------
# Source files
#----------------------------------------------------------------------------------------------------------------------

set(SOURCES
    src/nvapidrssession.cpp
    src/nvapiwrapper.cpp
    )

#----------------------------------------------------------------------------------------------------------------------
# Target config
#----------------------------------------------------------------------------------------------------------------------

add_library(${PROJECT_NAME} ${HEADERS} ${SOURCES})
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_SOURCE_DIR}/externals)
