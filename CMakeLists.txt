# Collect PR-Lib source files
file(GLOB_RECURSE PRLIB_SRCS 
    "src/*.cpp"
    "src/*.c"
)

idf_component_register(
    SRCS ${PRLIB_SRCS}
    INCLUDE_DIRS "include" 
    REQUIRES espressif__arduino-esp32
             adafruit__adafruit-lis3mdl
             bluepad32
)

# Add compile definitions
target_compile_definitions(${COMPONENT_LIB} PUBLIC
    PRLIB_VERSION_MAJOR=1
    PRLIB_VERSION_MINOR=0
)