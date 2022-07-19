cmake_minimum_required(VERSION 3.5)
project(nlink_parser_interfaces)

# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/IotFrame0.msg"
  "msg/IotFrame0Node.msg"
  "msg/LinktrackAnchorframe0.msg"
  "msg/LinktrackAoaNode0.msg"
  "msg/LinktrackAoaNodeframe0.msg"
  "msg/LinktrackNode0.msg"
  "msg/LinktrackNode1.msg"
  "msg/LinktrackNode2.msg"
  "msg/LinktrackNode4Anchor.msg"
  "msg/LinktrackNode4Tag.msg"
  "msg/LinktrackNode5.msg"
  "msg/LinktrackNode6.msg"
  "msg/LinktrackNodeframe0.msg"
  "msg/LinktrackNodeframe1.msg"
  "msg/LinktrackNodeframe2.msg"
  "msg/LinktrackNodeframe3.msg"
  "msg/LinktrackNodeframe4.msg"
  "msg/LinktrackNodeframe5.msg"
  "msg/LinktrackNodeframe6.msg"
  "msg/LinktrackTag.msg"
  "msg/LinktrackTagframe0.msg"
  "msg/TofsenseCascade.msg"
  "msg/TofsenseFrame0.msg"
  "msg/TofsenseMFrame0.msg"
  "msg/TofsenseMFrame0Pixel.msg"
  DEPENDENCIES builtin_interfaces std_msgs
)
ament_export_dependencies(rosidl_default_runtime std_msgs)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # uncomment the line when a copyright and license is not present in all source files
  #set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # uncomment the line when this package is not in a git repo
  #set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package()
