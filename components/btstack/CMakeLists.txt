# ESP-IDF wrapper for bluepad32
set(BLUEPAD32_UP ${CMAKE_CURRENT_LIST_DIR}/upstream)

# Sources are under src/
file(GLOB BLUEPAD32_SRCS
     "${BLUEPAD32_UP}/*.c"
     "${BLUEPAD32_UP}/*.cpp")

idf_component_register(
  SRCS         ${BLUEPAD32_SRCS}
  INCLUDE_DIRS "${BLUEPAD32_UP}/"
  REQUIRES
    btstack
)