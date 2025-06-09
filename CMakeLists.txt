cmake_minimum_required(VERSION 3.10)
project(cpp_project VERSION 1.0)

# Set C++ standard
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Configure static linking
set(BUILD_SHARED_LIBS OFF CACHE BOOL "Build shared libraries" FORCE)


# Add source files
set(SOURCES
    src/main.cpp
)

# Create executable
add_executable(${PROJECT_NAME} ${SOURCES})

# Set compiler flags
if(MSVC)
    target_compile_options(${PROJECT_NAME} PRIVATE /W4)
    # Hide console window in Release builds
    #set_target_properties(${PROJECT_NAME} PROPERTIES
    #   LINK_FLAGS_RELEASE "/SUBSYSTEM:WINDOWS /ENTRY:mainCRTStartup"
    #)
else()
    target_compile_options(${PROJECT_NAME} PRIVATE -Wall -Wextra)
    target_link_options(${PROJECT_NAME} PRIVATE -static -static-libgcc -static-libstdc++)
    # Hide console window in Release builds for MinGW
    #set_target_properties(${PROJECT_NAME} PROPERTIES
    #    LINK_FLAGS_RELEASE "-mwindows"
    #)
    message(STATUS "Building statically linked executable")
endif()

# Install targets
install(TARGETS ${PROJECT_NAME}
    RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
) 