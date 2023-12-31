cmake_minimum_required(VERSION 3.22)
project(PROJECT_NAME)

set(CMAKE_C_STANDARD 23)

add_executable(${PROJECT_NAME} src/main.c)

set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake/modules)

set(SDL2_PATH "SDL2/x86_64-w64-mingw32")
set(SDL2_IMAGE_PATH "SDL2_image/x86_64-w64-mingw32")
set(SDL2_MIXER_PATH "SDL2_mixer/x86_64-w64-mingw32")
set(SDL2_TTF_PATH "SDL2_ttf/x86_64-w64-mingw32")

find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIR})
target_link_libraries(${PROJECT_NAME} ${SDL2_LIBRARY})

find_package(SDL2_image REQUIRED)
include_directories(${SDL2_IMAGE_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} ${SDL2_IMAGE_LIBRARIES})

find_package(SDL2_mixer REQUIRED)
include_directories(${SDL2_MIXER_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} ${SDL2_MIXER_LIBRARIES})

find_package(SDL2_ttf REQUIRED)
include_directories(${SDL2_TTF_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} ${SDL2_TTF_LIBRARIES})