cmake_minimum_required(VERSION 3.25)

project(portfai LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_executable(${PROJECT_NAME} "src/main.cpp")

add_library(binance
    src/binance/binance_client.cpp
)

target_include_directories(binance
    PUBLIC
        src
)

target_link_libraries(${PROJECT_NAME} PUBLIC binance)


