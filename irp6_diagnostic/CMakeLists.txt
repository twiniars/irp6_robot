cmake_minimum_required(VERSION 2.8.3)

project(irp6_diagnostic)

find_package(catkin REQUIRED COMPONENTS rtt_ros)

find_package(OROCOS-RTT REQUIRED)
find_package(Eigen3 REQUIRED)
find_package(orocos_kdl REQUIRED)

include_directories(${catkin_INCLUDE_DIRS}  ${EIGEN3_INCLUDE_DIR})

orocos_component(irp6_diagnostic src/Irp6Diagnostic.cpp)
target_link_libraries(irp6_diagnostic ${catkin_LIBRARIES} ${orocos_kdl_LIBRARIES})
add_dependencies(irp6_diagnostic ${catkin_EXPORTED_TARGETS})


orocos_generate_package()
