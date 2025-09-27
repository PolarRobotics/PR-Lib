# Collect all source files
file(GLOB_RECURSE COMPONENT_SRCS 
    "src/*.cpp"
    "src/*.c"
)

# Register the component
idf_component_register(
    SRCS ${COMPONENT_SRCS}
    INCLUDE_DIRS "include"
    PRIV_INCLUDE_DIRS "private_include"  # Optional: for internal headers
    REQUIRES arduino-esp32  # Add other component dependencies here
    # PRIV_REQUIRES some_private_dependency  # Optional: private dependencies
)

# Optional: Add compile definitions
target_compile_definitions(${COMPONENT_LIB} PUBLIC
    PRLIB_VERSION_MAJOR=1
    PRLIB_VERSION_MINOR=0
)

# Optional: Add compiler flags
target_compile_options(${COMPONENT_LIB} PRIVATE
    -Wall -Wextra
)