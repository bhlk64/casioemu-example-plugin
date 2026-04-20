cmake_minimum_required(VERSION 3.22)
project(ExampleDynamicPlugin)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_compile_definitions(IMGUI_API=)
add_compile_definitions(CASIOEMU_PLUGIN_API=1)

set(IMGUI_SOURCES
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui_draw.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui_tables.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui_widgets.cpp"
)

file(GLOB PLUGIN_SOURCES
    ${CMAKE_CURRENT_SOURCE_DIR}/*.cpp
)

add_library(ExamplePlugin SHARED 
    ${PLUGIN_SOURCES}
    ${IMGUI_SOURCES}
)

target_include_directories(ExamplePlugin PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui
)

target_link_libraries(ExamplePlugin PRIVATE log GLESv2)