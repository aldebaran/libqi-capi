# we still have tests about deprecated stuff, we don't want warnings about that
if ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "Clang" OR "${CMAKE_CXX_COMPILER_ID}" STREQUAL "GNU")
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wno-deprecated-declarations")
endif()

qi_create_gtest(test_c_bindings SRC test_c_bindings.cpp DEPENDS QIC GTEST TIMEOUT 10)
qi_create_gtest(test_c_future SRC test_c_future.cpp DEPENDS QIC GTEST TIMEOUT 10)
qi_create_gtest(test_c_signal SRC test_c_signal.cpp DEPENDS QIC GTEST TIMEOUT 10)
qi_create_gtest(test_c_properties SRC test_c_properties.cpp DEPENDS QIC GTEST TIMEOUT 10)
qi_create_gtest(test_c_values SRC test_c_values.cpp DEPENDS QIC GTEST TIMEOUT 10)
qi_create_gtest(test_c_application SRC test_c_application.cpp DEPENDS QIC GTEST TIMEOUT 10)
