# ESP-IDF wrapper for bluepad32
set(BTSTACK_UP ${CMAKE_CURRENT_LIST_DIR}/upstream)

# Sources are under src/
file(GLOB BTSTACK_SRCS
     "${BTSTACK_UP}/*.c"
     "${BTSTACK_UP}/*.cpp")

idf_component_register(
  SRCS         ${BTSTACK_SRCS}
  INCLUDE_DIRS "${BTSTACK_UP}/"
  REQUIRES
    btstack
)