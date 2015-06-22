cmake_minimum_required(VERSION 2.8)
project (ka9q-fec)
 
ADD_DEFINITIONS(-D_SCL_SECURE_NO_WARNINGS)

set(CMAKE_BUILD_TYPE Release)

set(PROJECT_MAIN_SRCS 
	${CMAKE_CURRENT_SOURCE_DIR}/decode_rs_char.c
	${CMAKE_CURRENT_SOURCE_DIR}/encode_rs_char.c
	${CMAKE_CURRENT_SOURCE_DIR}/init_rs_char.c
)

 
add_library(${PROJECT_NAME} SHARED ${PROJECT_MAIN_SRCS})

### OS specific stuff ###
if(NOT WIN32)
	install(TARGETS ${PROJECT_NAME} LIBRARY DESTINATION lib)
	install(DIRECTORY ../include/ DESTINATION include/${PROJECT_NAME})
endif()
#########################

# Post-build copy of lib binary to lib folder
#add_custom_command(TARGET logga POST_BUILD 
					#COMMAND "${CMAKE_COMMAND}" -E copy 
					#"$<TARGET_FILE:logga>"
					#"../../lib/$<TARGET_FILE_NAME:logga>" 
					#COMMENT "Copying to lib directory")
