##############################################################################
# CMake
##############################################################################

cmake_minimum_required(VERSION 2.8.3)
project(rocon_app_manager_msgs)

##############################################################################
# Dependencies
##############################################################################

find_package(catkin REQUIRED COMPONENTS genmsg)

##############################################################################
# Messgaes
##############################################################################

add_message_files(
  DIRECTORY msg
  FILES
  KeyValue.msg
  PairingClient.msg
  Icon.msg
  App.msg
  AppList.msg
  Constants.msg
  ErrorCodes.msg
  Remapping.msg
  PlatformInfo.msg
)

add_service_files(
  DIRECTORY srv
  FILES
  GetAppList.srv
  GetPlatformInfo.srv
  Init.srv
  Invite.srv
  SimpleInvite.srv
  StartApp.srv
  Status.srv
  StopApp.srv
)

generate_messages(DEPENDENCIES)

##############################################################################
# Package
##############################################################################

catkin_package(CATKIN_DEPENDS message_runtime)
