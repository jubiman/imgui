# Dear Imgui cmake build script

cmake_minimum_required(VERSION 3.10)
project(imgui)

set(IMGUI_SOURCES
    imgui.cpp
    imgui_demo.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
    backends/imgui_impl_glfw.cpp
    backends/imgui_impl_vulkan.cpp
)

add_library(imgui STATIC ${IMGUI_SOURCES})
target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_compile_features(imgui PUBLIC cxx_std_11)
# Ignore warnings from imgui
target_compile_options(imgui PRIVATE -w)
