add_library(vector INTERFACE)
target_sources(
  vector
  INTERFACE
    FILE_SET HEADERS
    BASE_DIRS ${CMAKE_SOURCE_DIR}/include
    FILES ${CMAKE_SOURCE_DIR}/include/vector/vector.hpp
)

add_executable(main)
target_sources(main PRIVATE main.cpp)
target_link_libraries(
  main
  PRIVATE
    vector
    fmt::fmt
)
