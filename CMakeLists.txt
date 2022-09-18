cmake_minimum_required(VERSION 3.8)
message(${CMAKE_VERSION})

set(CMAKE_TOOLCHAIN_FILE "C:/dev/Projects/embedded_cmake/sam4e.cmake")

project("SAM-CMAKE")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/archive")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")


# Setup binary
set(EXECUTABLE_NAME "myproj")
add_sam_executable(${EXECUTABLE_NAME} "main.c" "Device_Startup/system_sam4e.c" "Device_Startup/startup_sam4e.c")

generate_binary_file(${EXECUTABLE_NAME})
display_size(${EXECUTABLE_NAME})
