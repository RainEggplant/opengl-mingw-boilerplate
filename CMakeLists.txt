cmake_minimum_required(VERSION 3.10)
project(opengl-mingw-boilerplate)

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)

# Source and external package files
set(SRC_DIR "${CMAKE_CURRENT_SOURCE_DIR}/src")
set(EXT_DIR "${CMAKE_CURRENT_SOURCE_DIR}/external")
aux_source_directory(${SRC_DIR} SOURCES)
set(GLFW_DIR "${EXT_DIR}/glfw")
set(GLAD_DIR "${EXT_DIR}/glad")
set(GLM_DIR "${EXT_DIR}/glm")
set(SOIL_DIR "${EXT_DIR}/soil")
set(FREETYPE_DIR "${EXT_DIR}/freetype")
link_directories(${GLFW_DIR}/lib ${SOIL_DIR}/lib ${FREETYPE_DIR}/lib)

# Add the executable
add_executable(${PROJECT_NAME} ${SOURCES})
target_include_directories(${PROJECT_NAME} PRIVATE "${SRC_DIR}")
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 17)

# Libraries
# GLFW
target_link_libraries(${PROJECT_NAME} glfw3)
target_include_directories(${PROJECT_NAME} PRIVATE "${GLFW_DIR}/include")
target_compile_definitions(${PROJECT_NAME} PRIVATE "GLFW_INCLUDE_NONE")

# GLAD
add_library("glad" "${GLAD_DIR}/src/glad.c")
target_include_directories("glad" PRIVATE "${GLAD_DIR}/include")
target_include_directories(${PROJECT_NAME} PRIVATE "${GLAD_DIR}/include")
target_link_libraries(${PROJECT_NAME} "glad" "${CMAKE_DL_LIBS}")

# GLM
target_include_directories(${PROJECT_NAME} PRIVATE "${GLM_DIR}")

# SOIL
target_link_libraries(${PROJECT_NAME} SOIL)
target_link_libraries(${PROJECT_NAME} opengl32)
target_include_directories(${PROJECT_NAME} PRIVATE "${SOIL_DIR}/include")

# Freetype
target_link_libraries(${PROJECT_NAME} freetype)
target_include_directories(${PROJECT_NAME} PRIVATE "${FREETYPE_DIR}/include")
