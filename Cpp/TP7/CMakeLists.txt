cmake_minimum_required( VERSION 3.0 )
project( TP_CPP )
set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -Wall -Wextra" )
set( CMAKE_BUILD_TYPE Debug )

find_package( PkgConfig REQUIRED )
pkg_check_modules( PKG REQUIRED gtkmm-2.4 cpputest )
include_directories( ${PKG_INCLUDE_DIRS} )

add_executable( main_image.out src/main_image.cpp src/Image.cpp )
target_link_libraries( main_image.out ${PKG_LIBRARIES} )

add_executable( main_test.out src/main_test.cpp 
    src/Image.cpp  )
target_link_libraries( main_test.out ${PKG_LIBRARIES} )

