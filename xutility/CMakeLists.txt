aux_source_directory(${CMAKE_CURRENT_SOURCE_DIR} Root_src)
aux_source_directory(${CMAKE_CURRENT_SOURCE_DIR}/log log_src)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/log)

MESSAGE(STATUS "This is BINARY dir " ${PROJECT_BINARY_DIR})
MESSAGE(STATUS "This is SOURCE dir " ${PROJECT_SOURCE_DIR})
MESSAGE(STATUS "This is CMAKE_INTDIR " ${CMAKE_INTDIR})

set(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)

add_library(xutility SHARED ${log_src})

add_definitions(-DUTILITY_EXPORTS)
set_target_properties(xutility PROPERTIES OUTPUT_NAME "xutility")