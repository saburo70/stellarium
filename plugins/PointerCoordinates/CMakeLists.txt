SET(POINTERCOORDINATES_MAJOR "0")
SET(POINTERCOORDINATES_MINOR "3")
SET(POINTERCOORDINATES_PATCH "0")
SET(POINTERCOORDINATES_VERSION "${POINTERCOORDINATES_MAJOR}.${POINTERCOORDINATES_MINOR}.${POINTERCOORDINATES_PATCH}")

IF(APPLE)
     SET(CMAKE_INSTALL_PREFIX $ENV{HOME}/Library/Application\ Support/Stellarium)
ElSE(APPLE)
     SET(CMAKE_INSTALL_PREFIX $ENV{HOME}/.stellarium)
ENDIF(APPLE)

ADD_DEFINITIONS(-DPOINTERCOORDINATES_PLUGIN_VERSION="${POINTERCOORDINATES_VERSION}")
ADD_DEFINITIONS(-DPOINTERCOORDINATES_PLUGIN_LICENSE="GNU GPLv2 or later")

ADD_SUBDIRECTORY( src )

INSTALL(FILES DESTINATION "modules/PointerCoordinates")


