#生成的子项目名称
project(Shaders) 

#glad glfw 包含路径
set(GLAD_PATH ../../3rdParty/glad/include)
set(GLFW_PATH ../../3rdParty/glfw-3.3.8/include)
include_directories(${GLAD_PATH} ${GLFW_PATH})

#搜索对应的头文件 并存储在 HEADER_FILES变量中
file(GLOB HEADER_FILES ./*.h ${GLFW_PATH}/GLFW/glfw3.h ${GLAD_PATH}/glad/glad.h)
#file(GLOB HEADER_FILES ./*.h)

#搜索对应的CPP文件 并存储在 SRC_FILES_FILES变量中
file(GLOB_RECURSE SRC_FILES ./*.cpp ../../3rdParty/glad/src/*.c)

#链接库路径
link_directories(../../3rdParty/glfw-3.3.8/lib/Release)

#将之前找到的文件导入到项目中，指定生成的文件类型 (.exe)
add_executable (${PROJECT_NAME} ${HEADER_FILES} ${SRC_FILES})

#链接库
target_link_libraries(${PROJECT_NAME} glfw3 opengl32)