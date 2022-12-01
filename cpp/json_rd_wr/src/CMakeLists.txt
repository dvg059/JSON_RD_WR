cmake_minimum_required(version 3.8)

set(This JSON_RD_WR)

project(${This} C CXX)

set(MAKE_C_STANDARD 99)
set(MAKE_CXX_STANDARD 11)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

enable_testing()
add_subdirectory(googletest)

set(Headers
    json_rd_wr.h    
)


set(Sources
    main.cpp
)

add_library(${This} STATIC ${Sources} ${Headers})

add_subdirectory(test)
