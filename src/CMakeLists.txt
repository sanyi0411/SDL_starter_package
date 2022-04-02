add_executable(${PROJECT_NAME} main.cpp)

add_dependencies(${PROJECT_NAME} SDL2main SDL2)

target_link_directories(${PROJECT_NAME} PUBLIC 
                        "${CMAKE_BINARY_DIR}/lib"
                        "${CMAKE_BINARY_DIR}/lib/${CMAKE_BUILD_TYPE_INIT}")


if(MSVC)
    if("${CMAKE_BUILD_TYPE_INIT}" STREQUAL Release)
        target_link_libraries(${PROJECT_NAME} PUBLIC SDL2)
        target_link_libraries(${PROJECT_NAME} PUBLIC SDL2main)
    else()
        target_link_libraries(${PROJECT_NAME} PUBLIC SDL2d)
        target_link_libraries(${PROJECT_NAME} PUBLIC SDL2maind)
    endif()
elseif(UNIX AND NOT APPLE)
    target_link_libraries(${PROJECT_NAME} PUBLIC libSDL2)
    target_link_libraries(${PROJECT_NAME} PUBLIC libSDL2main)
endif()
