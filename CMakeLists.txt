
# Collect PR-Lib source files
file(GLOB_RECURSE PRLIB_SRCS 
    "src/*.cpp"
    "src/*.c"
)

# Collect PS5-esp32 source files
# file(GLOB_RECURSE PS5_SRCS 
#     "lib/ps5-esp32-main/src/*.cpp"
#     "lib/ps5-esp32-main/src/*.c"
# )

# Collect FastLED source files
# file(GLOB_RECURSE FASTLED_SRCS 
#     "lib/FastLED/src/*.cpp"
#     "lib/FastLED/src/*.c"
# )

# Collect Adafruit LIS3MDL source files
# file(GLOB_RECURSE LIS3MDL_SRCS 
#     "lib/Adafruit LIS3MDL/*.cpp"
#     "lib/Adafruit LIS3MDL/*.c"
# )

# Combine all sources
set(ALL_SRCS ${PRLIB_SRCS})
# ${PS5_SRCS} ${FASTLED_SRCS} ${LIS3MDL_SRCS})

idf_component_register(
    SRCS ${ALL_SRCS}
    INCLUDE_DIRS "include" 
                "lib/USBSabertooth"
                #  "lib/ps5-esp32-main/src"      # PS5 headers
                #  "lib/FastLED/src"    # FastLED headers
                #  "lib/Adafruit LIS3MDL" # Adafruit LIS3MDL headers
    REQUIRES espressif__arduino-esp32
)

# Add compile definitions
target_compile_definitions(${COMPONENT_LIB} PUBLIC
    PRLIB_VERSION_MAJOR=1
    PRLIB_VERSION_MINOR=0
)