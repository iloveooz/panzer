cmake_minimum_required(VERSION 3.12)
project(panzer)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_COMPILER /usr/bin/g++)

set(SOURCE_FILES main.cpp)
add_executable(panzer main.cpp)

set(EXECUTABLE_NAME ${PROJECT_NAME})

# detect and add SFML to the project
set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake_modules" ${CMAKE_MODULE_PATH})
find_package(SFML 2 REQUIRED system window graphics network audio)

if (SFML_FOUND)
    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(${EXECUTABLE_NAME} ${SFML_LIBRARIES})
endif()










