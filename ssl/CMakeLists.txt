
file(GLOB SRCS *.c)

include_directories(../crypto/)

add_library(eay32 STATIC ${SRCS})
