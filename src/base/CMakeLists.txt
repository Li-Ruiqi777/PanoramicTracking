add_library(lib_base INTERFACE)

# 设置该库的头文件目录
target_include_directories(lib_base INTERFACE 
    ${CMAKE_CURRENT_SOURCE_DIR})