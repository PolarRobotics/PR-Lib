file(GLOB_RECURSE USBSABERTOOTH_SOURCES "*.cpp" "*.c")
idf_component_register(SRCS ${USBSABERTOOTH_SOURCES}
                       INCLUDE_DIRS "."
                       REQUIRES espressif__arduino-esp32)