# components/autowp_mcp2515/CMakeLists.txt
set(MCP2515_UP ${CMAKE_CURRENT_LIST_DIR}/upstream)

file(GLOB MCP2515_SRCS
     "${MCP2515_UP}/*.cpp")

idf_component_register(
  SRCS         ${MCP2515_SRCS}
  INCLUDE_DIRS "${MCP2515_UP}"
  REQUIRES     espressif__arduino-esp32
)

