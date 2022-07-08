cmake_minimum_required(VERSION 2.8.12)

PROJECT(ROCKWIN_DEMO_SRC)
include(CheckCXXCompilerFlag)
CHECK_CXX_COMPILER_FLAG("-std=c++11" COMPILER_SUPPORTS_CXX11)
#set(GCC_COMPILER_PATH /home/huangzihan/linux-release/youdao_1109/buildroot/output/rockchip_rv1126_rv1109/host)
#set(CMAKE_C_COMPILER ${GCC_COMPILER_PATH}/bin/arm-linux-gnueabihf-gcc)
#set(CMAKE_CXX_COMPILER ${GCC_COMPILER_PATH}/bin/arm-linux-gnueabihf-g++)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wl,--copy-dt-needed-entries")

include_directories(./include)
set(DEMO_SRC
      window.cpp
)

add_executable(window ${DEMO_SRC})
#target_include_directories(window PRIVATE ${CMAKE_SOURCE_DIR}/include)

target_link_libraries(window -lglfw -lGLEW -lGL)

