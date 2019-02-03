cmake_minimum_required (VERSION 2.6)
project (WasmerCApiTests)

add_executable(test-instantiate test-instantiate.c)
add_executable(test-import-function test-import-function.c)

target_link_libraries(test-instantiate
        general "${CMAKE_SOURCE_DIR}/../../../target/debug/libwasmer_runtime_c_api.dylib")

target_link_libraries(test-import-function
        general "${CMAKE_SOURCE_DIR}/../../../target/debug/libwasmer_runtime_c_api.dylib")

enable_testing()
add_test(test-instantiate test-instantiate)
add_test(test-import-function test-import-function)
