cmake_minimum_required(VERSION 3.15)

set(This Example)
project(${This} C CXX)

set(CMAKE_C_STANDARD 99)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

enable_testing()

include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/refs/heads/main.zip
)
FetchContent_MakeAvailable(googletest)

set(Headers 
    Example.hpp
)
set(Sources 
    Example.cpp 
)

add_library(${This} STATIC ${Sources} ${Headers})

add_subdirectory(test)



