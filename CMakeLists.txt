cmake_minimum_required(VERSION 3.10)

# Project name — зміню це за бажанням
project(MyProject LANGUAGES C CXX)

# Встановити стандарт C++
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# За замовчуванням Release, якщо не вказано
if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

# Додати підкаталог src, якщо він існує
if(EXISTS ${CMAKE_SOURCE_DIR}/src/CMakeLists.txt)
  add_subdirectory(src)
endif()

# Встановлення шляхів за GNUInstallDirs
include(GNUInstallDirs)

# Приклад простого таргету (коментуйте/видаляйте за потреби)
# add_executable(${PROJECT_NAME} src/main.cpp)
# install(TARGETS ${PROJECT_NAME} RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})