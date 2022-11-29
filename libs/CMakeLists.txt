cmake_minimum_required(VERSION 3.6)
project(Math)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++17")

set(SOURCE_FILES MathLibrary.cpp MathLibrary.hpp)

add_library(Math STATIC ${SOURCE_FILES})
add_library(Math_ SHARED ${SOURCE_FILES})



# # add the library that runs
# add_library(MathLibrary MathLibrary.cxx)

# # state that anybody linking to us needs to include the current source dir
# # to find MathLibrary.h, while we don't.
# target_include_directories(MathLibrary
#                            INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}
#                            )

# # should we use our own math functions
# option(USE_MYMATH "Use tutorial provided math implementation" ON)
# if(USE_MYMATH)

#   target_compile_definitions(MathFunctions PRIVATE "USE_MYMATH")

#   # first we add the executable that generates the table
#   add_executable(MakeTable MakeTable.cxx)

#   # add the command to generate the source code
#   add_custom_command(
#     OUTPUT ${CMAKE_CURRENT_BINARY_DIR}/Table.h
#     COMMAND MakeTable ${CMAKE_CURRENT_BINARY_DIR}/Table.h
#     DEPENDS MakeTable
#     )

#   # library that just does sqrt
#   add_library(SqrtLibrary STATIC
#               mysqrt.cxx
#               ${CMAKE_CURRENT_BINARY_DIR}/Table.h
#               )

#   # state that we depend on our binary dir to find Table.h
#   target_include_directories(SqrtLibrary PRIVATE
#                              ${CMAKE_CURRENT_BINARY_DIR}
#                              )

#   target_link_libraries(MathFunctions PRIVATE SqrtLibrary)
# endif()

# # define the symbol stating we are using the declspec(dllexport) when
# # building on windows
# target_compile_definitions(MathFunctions PRIVATE "EXPORTING_MYMATH")

# # install rules
# set(installable_libs MathFunctions)
# if(TARGET SqrtLibrary)
#   list(APPEND installable_libs SqrtLibrary)
# endif()
# install(TARGETS ${installable_libs} DESTINATION lib)
# install(FILES MathFunctions.h DESTINATION include)