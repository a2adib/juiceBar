cmake_minimum_required(VERSION 3.10)
project(OpenGLTest)

set(CMAKE_CXX_STANDARD 17)

# Find GLFW
find_package(glfw3 REQUIRED)

# Include directories (Homebrew paths + your local glad headers)
include_directories(/opt/homebrew/include include)

# Create the executable
add_executable(OpenGLTest src/main.cpp src/glad.c)

# Link libraries (Note: macOS needs Cocoa, IOKit, and CoreVideo)
target_link_libraries(OpenGLTest glfw "-framework OpenGL" "-framework Cocoa" "-framework IOKit" "-framework CoreVideo")