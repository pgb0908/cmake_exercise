cmake_minimum_required(VERSION 3.10)
project(cmake_exercise)

set(CMAKE_CXX_STANDARD 17)

include(cmake/check-compiler-flags.cmake)

message(STATUS ${CMAKE_SOURCE_DIR})         # -- Root
message(STATUS ${CMAKE_CURRENT_SOURCE_DIR}) # -- Root

add_executable(cmake_exercise main.cpp)

target_sources(cmake_exercise PRIVATE foo.cpp)


#[[# 단일 파일을 지정된 폴더에 설치
install(FILE            LICENSE     # ReadMe와 같이 라이브러리와 함께 배포되어야 하는 파일들
        DESTINATION     ./install/
        )]]

# 폴더 전체를 설치
install(DIRECTORY       include     # 헤더 파일들을 통째로 옮긴다
        DESTINATION     ./install/
        )