cmake_minimum_required(VERSION 2.8.8)
set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

project(bleu-champ CXX)
SET(CMAKE_CXX_FLAGS " -std=c++11 -g -O3 -funroll-loops -Wno-unused-result -Wno-deprecated")

include_directories(${bleu-champ_SOURCE_DIR})
set(EXT_LIBS)

find_package(Boost COMPONENTS program_options timer system)
if(Boost_FOUND)
    include_directories(${Boost_INCLUDE_DIRS})
    set(EXT_LIBS ${EXT_LIBS} ${Boost_LIBRARIES})
else(Boost_FOUND)
    message(SEND_ERROR "Cannot find Boost libraries. Terminating." )
endif(Boost_FOUND)

include_directories(${bleu-champ_SOURCE_DIR}/src)
include_directories(${bleu-champ_SOURCE_DIR}/util)
add_subdirectory(src)
add_subdirectory(util)