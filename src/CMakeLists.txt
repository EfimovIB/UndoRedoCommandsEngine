#
# Static lib command-engine-lib
#

file(GLOB SOURCES "*.hpp" "*.cpp")
get_filename_component(full_path_main_cpp ${CMAKE_CURRENT_SOURCE_DIR}/main.cpp ABSOLUTE)
list(REMOVE_ITEM SOURCES "${full_path_main_cpp}")

add_library(command-engine-lib STATIC ${SOURCES})

#
# app
#

add_executable(app main.cpp)
target_link_libraries(app command-engine-lib)
