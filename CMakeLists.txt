cmake_minimum_required(VERSION 3.25.0)
project(PanoramicTracking
        VERSION 0.0.1
        DESCRIPTION "Real-time panoramic video stitching and object tracking"
        HOMEPAGE_URL "https://github.com/Li-Ruiqi777/PanoramicTracking"
        LANGUAGES CXX
)
set(CMAKE_CXX_STANDARD 17)
list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)
include(Function)
#三方库
## OpenCV
list(APPEND CMAKE_PREFIX_PATH "F:/ThirdPart/OpenCV")
find_package(OpenCV REQUIRED)
## PLOG
list(APPEND CMAKE_PREFIX_PATH "F:/ThirdPart/plog")
find_package(plog REQUIRED)

# 变量和目录设置
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)
list(APPEND ALL_INCLUDE_DIRS
        ${OpenCV_INCLUDE_DIRS}
        F:/ThirdPart/plog/include
)
list(APPEND ALL_LIBS
        ${OpenCV_LIBRARIES}
)


# 添加子目录
add_subdirectory(src)
add_subdirectory(test)
