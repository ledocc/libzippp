
add_executable(zippp_test "tests.cpp")
target_include_directories(zippp_test PUBLIC "${PROJECT_SOURCE_DIR}/src")
target_link_libraries(zippp_test zippp)
