# Project name
PROJECT(Audio_Components)

# CMake required version must be >= 2.6
cmake_minimum_required(VERSION 2.6)

FIND_PACKAGE(Boost REQUIRED)
include_directories(${Boost_INCLUDE_DIR})

FIND_PACKAGE(DisCODe REQUIRED)

set(CMAKE_MODULE_PATH ${DisCODe_DIR}/share/DisCODe ${CMAKE_MODULE_PATH})

include(DisCODeMacros)

# set default install prefix
IF(CMAKE_INSTALL_PREFIX_INITIALIZED_TO_DEFAULT)
  SET(CMAKE_INSTALL_PREFIX
      ${DisCODe_DIR} CACHE PATH "${CMAKE_PROJECT_NAME} install prefix" FORCE
  )
ENDIF(CMAKE_INSTALL_PREFIX_INITIALIZED_TO_DEFAULT)

ADD_COMPONENT(AudioFFT)
ADD_COMPONENT(AudioPreemphasis)
ADD_COMPONENT(AudioSpectrogram)

ADD_COMPONENT(WAVSource)

ADD_COMPONENT(Speakers)
ADD_COMPONENT(WAVSink)
