
add_library(retdec-utils STATIC
	alignment.cpp
	byte_value_storage.cpp
	binary_path.cpp
	conversion.cpp
	dynamic_buffer.cpp
	file_io.cpp
	filesystem_path.cpp
	math.cpp
	memory.cpp
	string.cpp
	system.cpp
	time.cpp
)
target_link_libraries(retdec-utils whereami)
target_include_directories(retdec-utils PUBLIC ${PROJECT_SOURCE_DIR}/include/)
target_include_directories(retdec-utils PUBLIC ${PROJECT_SOURCE_DIR}/deps/)

# Disable the min() and max() macros to prevent errors when using e.g.
# std::numeric_limits<...>::max()
# (http://stackoverflow.com/questions/1904635/warning-c4003-and-errors-c2589-and-c2059-on-x-stdnumeric-limitsintmax).
# Any target that includes "windows.h" needs to define this.
if(MSVC)
	target_compile_definitions(retdec-utils PUBLIC NOMINMAX)
endif()
