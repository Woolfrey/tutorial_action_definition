cmake_minimum_required(VERSION 3.8)
project(tutorial_action_definition)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

####################################################################################################
#                                             Dependencies                                         #
####################################################################################################
find_package(ament_cmake REQUIRED)

if(BUILD_TESTING)
   find_package(ament_lint_auto REQUIRED)
   set(ament_cmake_copyright_FOUND TRUE)
   set(ament_cmake_cpplint_FOUND TRUE)
   ament_lint_auto_find_test_dependencies()
endif()

####################################################################################################
#                                          Generate Actions                                        #
####################################################################################################

find_package(rosidl_default_generators REQUIRED)                                                    # Needed to convert .action files to C++

rosidl_generate_interfaces(${PROJECT_NAME}
                           "action/Haiku.action")

ament_package()
