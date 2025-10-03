cmake_minimum_required(VERSION 3.20)

set(HEAD_DIR_LIST
    $ENV{STM32StdLib_ROOT}/inc
    $ENV{STM32StdLib_ROOT}/CMSIS
)

file(GLOB_RECURSE SRC_LIST
    $ENV{STM32StdLib_ROOT}/src/*.c
    $ENV{STM32StdLib_ROOT}/CMSIS/*.c
)