set(SOURCES file_server.c mount_spiffs.c)
if(${CMAKE_PROJECT_NAME})
  idf_component_register(SRCS ${SOURCES},
      INCLUDE_DIRS include,
      REQUIRES esp_timer driver spiffs timer esp_timer esp_event nvs_flash espWifi)
else()
  cmake_minimum_required(VERSION 3.16)
  set(CMAKE_CXX_STANDARD 17)
  set(EXTRA_COMPONENT_DIRS include)
  include($ENV{IDF_PATH}/tools/cmake/project.cmake)
  project(espFileServer)
endif()