project(beast_advanced_server)
cmake_minimum_required(VERSION 3.7)

set(CMAKE_CXX_STANDARD 11)



set(BOOST_ROOT /home/sean/room/boost/boost_1_68_0) # 设置boost库搜索路径

set(Boost_NO_SYSTEM_PATHS ON) # 只搜索上语句设置的搜索路径



# find_package(Boost COMPONENTS regex system REQUIRED)
find_package(Boost COMPONENTS system REQUIRED)
find_package(Threads REQUIRED)

if(Boost_FOUND)

include_directories(${Boost_INCLUDE_DIRS})

MESSAGE( STATUS "Boost_INCLUDE_DIRS = ${Boost_INCLUDE_DIRS}.")

MESSAGE( STATUS "Boost_LIBRARIES = ${Boost_LIBRARIES}.")

MESSAGE( STATUS "Boost_LIB_VERSION = ${Boost_LIB_VERSION}.")



add_executable(advanced_server advanced_server.cpp)

target_link_libraries (advanced_server ${Boost_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})

endif()
