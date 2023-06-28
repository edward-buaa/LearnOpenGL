#对CMake版本进行限制
cmake_minimum_required(VERSION 3.15)

#设置解决方案名称
project(LearnOpenGL)

#添加子目录
# - 参数1 是用来指定需要索引的源文件目录 
# - 参数2 用来指定项目的名称
add_subdirectory(src/helloWindow HelloWindow)
#add_subdirectory(Server MyServer)