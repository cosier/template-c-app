cmake_minimum_required(VERSION 3.6)
project(${APP_EXE_NAME})

# This project uses C11 Standard
set( CMAKE_C_STANDARD 11 )

# Treat all warnings as intense errors.
set( CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Werror")

# Main executable has a single file
SET ( SRC_MAIN main.c )

# Setup main executable for this project
add_executable("${APP_EXE_NAME}" ${SRC_MAIN})

include_directories(
  ${VENDOR}/ubelt/src
  ${APP_ROOT}/src)

# Link Library support
target_link_libraries( ${APP_EXE_NAME} ${APP_LIB_NAME} )

install(TARGETS ${APP_EXE_NAME}
  RUNTIME DESTINATION bin)

