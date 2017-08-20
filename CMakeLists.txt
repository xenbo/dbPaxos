cmake_minimum_required(VERSION 3.9)
project(paxos)

set(CMAKE_CXX_STANDARD 11)

include_directories(src/algorithm src/checkpoint src/comm src/communicate src/config src/logstorage src/master src/node src/sm-base src/tools src/utils src/ut src/test include)


AUX_SOURCE_DIRECTORY(src/algorithm  DIR_SRCS1)
AUX_SOURCE_DIRECTORY(src/node  DIR_SRCS2)
AUX_SOURCE_DIRECTORY(src/checkpoint  DIR_SRCS3)
AUX_SOURCE_DIRECTORY(src/comm  DIR_SRCS4)
AUX_SOURCE_DIRECTORY(src/communicate  DIR_SRCS5)
AUX_SOURCE_DIRECTORY(src/config  DIR_SRCS6)
AUX_SOURCE_DIRECTORY(src/logstorage  DIR_SRCS7)
AUX_SOURCE_DIRECTORY(src/sm-base  DIR_SRCS8)
AUX_SOURCE_DIRECTORY(src/master  DIR_SRCS9)
AUX_SOURCE_DIRECTORY(src/tools  DIR_SRCS10)
AUX_SOURCE_DIRECTORY(src/ut  DIR_SRCS11)
AUX_SOURCE_DIRECTORY(src/utils  DIR_SRCS12)
AUX_SOURCE_DIRECTORY(src/test  DIR_SRCS13)

set(SOURCE_FILES main.cpp ${DIR_SRCS1} ${DIR_SRCS2} ${DIR_SRCS3} ${DIR_SRCS4} ${DIR_SRCS5} ${DIR_SRCS6} ${DIR_SRCS7} ${DIR_SRCS8} ${DIR_SRCS9} ${DIR_SRCS10} ${DIR_SRCS11} ${DIR_SRCS3} ${DIR_SRCS12})
add_executable(paxos ${SOURCE_FILES})