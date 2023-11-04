cmake_minimum_required(VERSION 3.8)
project(chess_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)

find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/ChessBoardFEN.msg"
  "msg/ChessMoveUCI.msg"
  "msg/ChessTime.msg"
  "msg/Color.msg"
  "msg/EngineInfo.msg"
  "msg/GameConfig.msg"

  "action/EvaluateMove.action"
)

ament_package()
