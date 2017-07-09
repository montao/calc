cmake_minimum_required(VERSION 3.7)
project(calc)

set(CMAKE_C_STANDARD 99)

find_package(BISON)
find_package(FLEX)


BISON_TARGET(MyParser fb1-5.y ${CMAKE_CURRENT_BINARY_DIR}/parser.c)
FLEX_TARGET(MyScanner fb1-5.l  ${CMAKE_CURRENT_BINARY_DIR}/lexer.c)
ADD_FLEX_BISON_DEPENDENCY(MyScanner MyParser)


include_directories(${CMAKE_CURRENT_BINARY_DIR})

add_executable(calc

        ${BISON_MyParser_OUTPUTS}
        ${FLEX_MyScanner_OUTPUTS}
        )
target_link_libraries(calc fl)