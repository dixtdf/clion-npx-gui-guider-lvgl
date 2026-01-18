cmake_minimum_required(VERSION 3.15)
project(lvgl_index_project C CXX)

# 1. 定义路径变量 (请根据你实际的 lvgl 源码路径修改)
set(LVGL_ROOT_DIR ${CMAKE_CURRENT_SOURCE_DIR}/nxp-demo/lvgl)
set(GG_PROJECT_DIR ${CMAKE_CURRENT_SOURCE_DIR}/nxp-demo)

# 2. 包含 LVGL 核心头文件
include_directories(
    ${LVGL_ROOT_DIR}
    ${LVGL_ROOT_DIR}/src
    ${LVGL_ROOT_DIR}/examples
)

# 3. 包含 GUI Guider 生成的代码路径
include_directories(
    ${GG_PROJECT_DIR}/custom
    ${GG_PROJECT_DIR}/generated
    ${GG_PROJECT_DIR}/generated/guider_fonts
    ${GG_PROJECT_DIR}/generated/guider_customer_fonts
    ${GG_PROJECT_DIR}/generated/images
)

# 4. 让 CMake 扫描所有源文件以便 CLion 建立索引
# 这里使用 GLOB_RECURSE 递归扫描所有 C 文件
file(GLOB_RECURSE SOURCES 
    "${LVGL_ROOT_DIR}/src/*.c"
    "${GG_PROJECT_DIR}/custom/*.c"
    "${GG_PROJECT_DIR}/custom/*.cpp"
    "${GG_PROJECT_DIR}/generated/*.c"
)

# 5. 定义一个伪可执行文件（仅用于激活 IDE 索引）
add_executable(lvgl_index ${SOURCES})

# 如果需要支持 LVGL 的配置，定义宏
add_definitions(-DLV_CONF_INCLUDE_SIMPLE)
# 这里的路径要指向你的 lv_conf.h 所在位置
include_directories(${GG_PROJECT_DIR})