cmake_minimum_required(VERSION 3.8)
project(paxos)

set(CMAKE_CXX_STANDARD 11)


include_directories(include)
include_directories(include/phxpaxos)
include_directories(src/algorithm)
include_directories(src/config)
include_directories(src/node)
include_directories(src/utils)
include_directories(src/logstorage)
include_directories(src/comm)
include_directories(src/sm-base)
include_directories(src/tools)
include_directories(src/checkpoint)
#include_directories(src/ut)
include_directories(src/communicate)
include_directories(src/communicate/tcp)
include_directories(src/master)


include_directories(src/test)
link_directories(/usr/local/lib64/)



AUX_SOURCE_DIRECTORY(src/algorithm SRC)
set(SOURCE_FILES ${SRC})

AUX_SOURCE_DIRECTORY(src/config SRC)
set(SOURCE_FILES ${SRC})

AUX_SOURCE_DIRECTORY(src/node SRC)
set(SOURCE_FILES ${SRC})

AUX_SOURCE_DIRECTORY(src/utils SRC)
set(SOURCE_FILES ${SRC})

AUX_SOURCE_DIRECTORY(src/logstorage SRC)
set(SOURCE_FILES ${SRC})

AUX_SOURCE_DIRECTORY(src/comm SRC)
set(SOURCE_FILES ${SRC})

AUX_SOURCE_DIRECTORY(src/sm-base SRC)
set(SOURCE_FILES ${SRC})

AUX_SOURCE_DIRECTORY(src/tools SRC)
set(SOURCE_FILES ${SRC})

#AUX_SOURCE_DIRECTORY(src/ut SRC)
#set(SOURCE_FILES ${SRC})

AUX_SOURCE_DIRECTORY(src/checkpoint SRC)
set(SOURCE_FILES ${SRC})

AUX_SOURCE_DIRECTORY(src/communicate SRC)
set(SOURCE_FILES ${SRC})

AUX_SOURCE_DIRECTORY(src/communicate/tcp SRC)
set(SOURCE_FILES ${SRC})

AUX_SOURCE_DIRECTORY(src/master SRC)
set(SOURCE_FILES ${SRC})



add_library(dbphxpaxos STATIC ${SOURCE_FILES})

AUX_SOURCE_DIRECTORY(src/test SRCTEST)
set(SOURCE_FILESTEST ${SRCTEST})

add_executable(paxos ${SOURCE_FILESTEST})
target_link_libraries(paxos dbphxpaxos leveldb protobuf pthread)