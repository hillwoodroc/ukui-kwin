if ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "GNU")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wno-int-to-pointer-cast")
endif()
if ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "Clang")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wno-int-to-void-pointer-cast")
endif()
include_directories(${CMAKE_SOURCE_DIR}/platformsupport/scenes/opengl)
add_library(eglx11common STATIC eglonxbackend.cpp)
target_link_libraries(eglx11common ukui-kwin)
