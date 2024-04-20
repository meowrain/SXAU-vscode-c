cmake_minimum_required(VERSION 3.29)
project(cmake-learn)
# 指定源文件目录
set(SRC_DIR "${PROJECT_SOURCE_DIR}/src")

# 获取源文件列表
file(GLOB_RECURSE SRC_FILES "${SRC_DIR}/*.c")

# 遍历源文件列表，为每个文件创建一个可执行文件
foreach(SRC_FILE ${SRC_FILES})
    # 获取源文件的文件名（不包含路径和扩展名）
    get_filename_component(EXEC_NAME ${SRC_FILE} NAME_WE)

    # 添加可执行文件
    add_executable(${EXEC_NAME} ${SRC_FILE})

    # 设置可执行文件的输出路径
    set_target_properties(${EXEC_NAME} PROPERTIES
        RUNTIME_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/bin"
    )
endforeach()
