cmake_minimum_required(VERSION 3.10)
project(imgui)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Add source files
set(IMGUI_SOURCES
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_demo.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_draw.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_tables.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_widgets.cpp
)

# Add header files
set(IMGUI_HEADERS
    ${CMAKE_CURRENT_SOURCE_DIR}/imconfig.h
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui.h
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_internal.h
    ${CMAKE_CURRENT_SOURCE_DIR}/imstb_rectpack.h
    ${CMAKE_CURRENT_SOURCE_DIR}/imstb_textedit.h
    ${CMAKE_CURRENT_SOURCE_DIR}/imstb_truetype.h
)

# Create static library
add_library(imgui STATIC ${IMGUI_SOURCES} ${IMGUI_HEADERS})

# Include directories
target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

# Optionally, you can add the backends if needed
# set(IMGUI_BACKENDS
#     ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_allegro5.cpp
#     ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_android.cpp
#     ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_dx10.cpp
#     ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_dx11.cpp
#     ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_dx9.cpp
#     ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_opengl3.cpp
#     ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_vulkan.cpp
#     ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_win32.cpp
# )

# # Add backends to the library
# target_sources(imgui PRIVATE ${IMGUI_BACKENDS})