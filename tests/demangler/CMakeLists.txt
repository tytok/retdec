set(RETDEC_TESTS_DEMANGLER_SOURCES
	gcc_tests.cpp
	msvc_tests.cpp
	borland_tests.cpp
	borland_context_tests.cpp
)

add_executable(retdec-tests-demangler ${RETDEC_TESTS_DEMANGLER_SOURCES})
target_link_libraries(retdec-tests-demangler retdec-demangler gmock_main)
install(TARGETS retdec-tests-demangler RUNTIME DESTINATION ${RETDEC_TESTS_DIR})
