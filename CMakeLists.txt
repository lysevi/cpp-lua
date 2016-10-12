cmake_minimum_required (VERSION 3.1)
set(PROJECT "dariadb-example")
project (${PROJECT} VERSION 0.1.0)

set(LUA_BUILD_AS_DLL  OFF)
set(BUILD_SHARED_LIBS ON)
set(BUILD_TESTING OFF)
set(LUA_BUILD_WLUA OFF)

add_subdirectory(lua)

INCLUDE_DIRECTORIES(lua/src)
INCLUDE_DIRECTORIES(lua/)


add_executable(example main.cpp)
target_link_libraries(example liblua_static)