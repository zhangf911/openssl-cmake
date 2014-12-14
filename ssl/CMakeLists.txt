
file(GLOB SRCS *.c)

include_directories(../crypto/)

add_library(ssleay32 STATIC ${SRCS})
