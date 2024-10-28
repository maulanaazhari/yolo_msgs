cmake_minimum_required(VERSION 3.0.2)
project(yolo_msgs)

find_package(catkin REQUIRED COMPONENTS geometry_msgs message_generation std_msgs)

include_directories(include)

add_message_files(
  DIRECTORY msg
  FILES
  Point2D.msg
  Vector2.msg
  Pose2D.msg
  BoundingBox2D.msg
  BoundingBox3D.msg
  Mask.msg
  KeyPoint2D.msg
  KeyPoint2DArray.msg
  KeyPoint3D.msg
  KeyPoint3DArray.msg
  Detection.msg
  DetectionArray.msg
)

generate_messages(DEPENDENCIES geometry_msgs std_msgs)

catkin_package(CATKIN_DEPENDS
  message_runtime
  std_msgs
  geometry_msgs
)

install(DIRECTORY include/${PROJECT_NAME}/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
  FILES_MATCHING PATTERN "*.h"
)