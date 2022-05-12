cmake_minimum_required(VERSION 3.15)
project(breakout)

find_library(OPENGL opengl)
# 添加头文件
set(GLEW_H /usr/local/Cellar/glew/2.2.0_1/include/GL)
set(GLFW_H /usr/local/Cellar/glfw/3.3.2/include/GLFW)
set(SOIL_H /opt/local/include/SOIL)
set(GLM_H /usr/local/Cellar/glm)
set(ASSIMP_H /usr/local/include)
set(FREETYPE_H /usr/local/Cellar/freetype/2.10.4/include/freetype2)
include_directories(${GLEW_H} ${GLFW_H} ${SOIL_H} ${GLM_H} ${ASSIMP_H} ${FREETYPE_H})

# 添加目标链接
set(GLEW_LINK /usr/local/Cellar/glew/2.2.0_1/lib/libGLEW.2.2.dylib)
set(GLFW_LINK /usr/local/Cellar/glfw/3.3.2/lib/libglfw.3.dylib)
set(SOIL_LINK /opt/local/lib/libSOIL.dylib)
set(ASSIMP_LINK /usr/local/lib/libassimp.3.1.1.dylib)
set(FREETYPE_LINK /usr/local/Cellar/freetype/2.10.4/lib/libfreetype.6.dylib)
link_libraries(${OPENGL} ${GLEW_LINK} ${GLFW_LINK} ${SOIL_LINK} ${ASSIMP_LINK} ${FREETYPE_LINK})

set(CMAKE_CXX_STANDARD 14)

add_executable(breakout main.cpp game.cpp resource_manager.cpp shader.cpp sprite_renderer.cpp game_object.cpp game_level.cpp ball_object_collisions.cpp particle_generator.cpp post_processor.cpp power_up.cpp text_renderer.cpp texture.cpp)