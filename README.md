# STM32F10x标准库
Version 3.6.0

# 使用方法
1. 将此项目下载之后，添加环境变量``STM32StdLib_ROOT``指向此文件夹
2. 在自己工程项目的CMakeLists.txt中添加库

```CMake
include($ENV{STM32StdLib_ROOT}/CMakeLists.txt)

# 在项目中添加头文件的地方加上变量'${HEAD_DIR_LIST}'，例如

target_include_directories(${CMAKE_PROJECT_NAME} PRIVATE
    ${include_DIRS}
    ${HEAD_DIR_LIST}
    $<$<COMPILE_LANGUAGE:C>: ${include_c_DIRS}>
    $<$<COMPILE_LANGUAGE:CXX>: ${include_cxx_DIRS}>
    $<$<COMPILE_LANGUAGE:ASM>: ${include_asm_DIRS}>
)

# 源文件同理

set(sources_SRCS
	${proj_src}
    ${SRC_LIST}
)
```
3. 如果没有定义芯片规格，可以在``CMSIS/stm32f10x.h``中65~72行选择自己的芯片规格取消注释即可。或者在项目CMakeList.txt中定义

```CMake
# STM32F103C8T6为例
add_definitions(
    -DUSE_STDPERIPH_DRIVER
    -DSTM32F10X_MD
    -DHSE_VALUE=8000000
)
```
模板工程参考，[点此跳转](/gitea/Liyuu_SK/STM32F10x-Template-Project)