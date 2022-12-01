cmake_minimum_required(version 3.8)

set(This JSON_RD_WR)

set(Sources
    json_rd_wr_test.cpp
)

add_executable((${This} ${Sources}))

target_link_libraries(${This} PUBLIC_HEADER
    gtest_main
    json_unit_test
    )

add_test(
    NAME ${This}
    COMMAND ${This}
)