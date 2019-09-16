cmake_minimum_required(VERSION 3.8)
project(FFMPEG_CPP_DEMO)
find_package(PkgConfig REQUIRED)
find_package(Threads REQUIRED)
find_library(AVCODEC_LIBRARY avcodec)
find_library(AVFORMAT_LIBRARY avformat)
find_library(AVUTIL_LIBRARY avutil)
find_library(AVFILTER_LIBRARY avfilter)
find_library(SWRESAMPLE_LIBRARY swresample)
find_library(SWSCALE_LIBRARY swscale)

set(CMAKE_CXX_STANDARD 11)

set(SOURCE_FILES_REMUX ffmpeg_remuxer.c)

link_directories(${GSTLIBS_LIBRARY_DIRS})

add_executable(ffmpeg_remuxer ${SOURCE_FILES_REMUX})

target_link_libraries(ffmpeg_remuxer ${AVCODEC_LIBRARY} ${AVFORMAT_LIBRARY} ${AVUTIL_LIBRARY} ${AVFILTER_LIBRARY})