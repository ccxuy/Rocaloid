project(SpeakerAna)
cmake_minimum_required(VERSION 2.8)

#set(CMAKE_VERBOSE_MAKEFILE ON)

aux_source_directory(RUtil SRC_LIST)
aux_source_directory(RUtil/IO SRC_LIST)
aux_source_directory(RUtil/Misc SRC_LIST)
aux_source_directory(RUtil/Structure SRC_LIST)
aux_source_directory(RFILE3 SRC_LIST)
aux_source_directory(RFILE3/CVDB3 SRC_LIST)
aux_source_directory(CVEANN SRC_LIST)
aux_source_directory(CVEANN/Network SRC_LIST)
aux_source_directory(CVEANN/Trainer SRC_LIST)
aux_source_directory(. SRC_LIST)
aux_source_directory(.. SRC_LIST)

link_directories(${PROJECT_SOURCE_DIR}/CVEDSP/)
link_libraries(CVEDSP)
link_libraries(m)

#Debug
#SET(CMAKE_C_FLAGS "-O0 -Wall -g")

#Release
SET(CMAKE_C_FLAGS "-O3 -ffast-math -Wall")

add_executable(${PROJECT_NAME} ${SRC_LIST})
