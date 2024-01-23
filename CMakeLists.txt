cmake_minimum_required(VERSION 3.12)
project(Test)

SET(CMAKE_EXPORT_COMPILE_COMMANDS ON)
add_executable(test main.cpp)

target_include_directories(test PRIVATE 
/Applications/CPLEX_Studio_Community2211/cplex/include
/Applications/CPLEX_Studio_Community2211/concert/include
)

target_link_directories(test PRIVATE
/Applications/CPLEX_Studio_Community2211/cplex/lib/arm64_osx/static_pic
/Applications/CPLEX_Studio_Community2211/concert/lib/arm64_osx/static_pic
)

target_link_libraries(test PRIVATE
    ilocplex
    concert
    cplex
    pthread
    m
    dl
)
