
cmake_minimum_required(VERSION 3.5)
project(boost_multi_index)
include(CMakePackageConfigHelpers)

find_package(boost_core)
find_package(boost_static_assert)
find_package(boost_functional)
find_package(boost_iterator)
find_package(boost_tuple)
find_package(boost_bind)
find_package(boost_mpl)
find_package(boost_move)
find_package(boost_detail)
find_package(boost_assert)
find_package(boost_smart_ptr)
find_package(boost_type_traits)
find_package(boost_preprocessor)
find_package(boost_foreach)
find_package(boost_integer)
find_package(boost_serialization)
find_package(boost_config)
find_package(boost_throw_exception)
find_package(boost_utility)

add_library(boost_multi_index INTERFACE
)
add_library(boost::multi_index ALIAS boost_multi_index)
set_property(TARGET boost_multi_index PROPERTY EXPORT_NAME multi_index)

target_include_directories(boost_multi_index INTERFACE
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
)

if(boost_core_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::core)
endif()
if(boost_static_assert_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::static_assert)
endif()
if(boost_functional_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::functional)
endif()
if(boost_iterator_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::iterator)
endif()
if(boost_tuple_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::tuple)
endif()
if(boost_bind_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::bind)
endif()
if(boost_mpl_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::mpl)
endif()
if(boost_move_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::move)
endif()
if(boost_detail_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::detail)
endif()
if(boost_assert_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::assert)
endif()
if(boost_smart_ptr_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::smart_ptr)
endif()
if(boost_type_traits_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::type_traits)
endif()
if(boost_preprocessor_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::preprocessor)
endif()
if(boost_foreach_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::foreach)
endif()
if(boost_integer_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::integer)
endif()
if(boost_serialization_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::serialization)
endif()
if(boost_config_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::config)
endif()
if(boost_throw_exception_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::throw_exception)
endif()
if(boost_utility_FOUND)
target_link_libraries(boost_multi_index INTERFACE boost::utility)
endif()



install(DIRECTORY include/ DESTINATION include)

install(TARGETS boost_multi_index EXPORT boost_multi_index-targets
    RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    INCLUDES DESTINATION include
)

install(EXPORT boost_multi_index-targets
  FILE boost_multi_index-targets.cmake
  NAMESPACE boost::
  DESTINATION lib/cmake/boost_multi_index
)

file(WRITE "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "include(CMakeFindDependencyMacro)")
if(boost_core_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_core)
")
endif()
if(boost_static_assert_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_static_assert)
")
endif()
if(boost_functional_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_functional)
")
endif()
if(boost_iterator_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_iterator)
")
endif()
if(boost_tuple_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_tuple)
")
endif()
if(boost_bind_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_bind)
")
endif()
if(boost_mpl_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_mpl)
")
endif()
if(boost_move_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_move)
")
endif()
if(boost_detail_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_detail)
")
endif()
if(boost_assert_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_assert)
")
endif()
if(boost_smart_ptr_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_smart_ptr)
")
endif()
if(boost_type_traits_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_type_traits)
")
endif()
if(boost_preprocessor_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_preprocessor)
")
endif()
if(boost_foreach_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_foreach)
")
endif()
if(boost_integer_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_integer)
")
endif()
if(boost_serialization_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_serialization)
")
endif()
if(boost_config_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_config)
")
endif()
if(boost_throw_exception_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_throw_exception)
")
endif()
if(boost_utility_FOUND)
file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
find_package(boost_utility)
")
endif()


file(APPEND "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake" "
include(\"\${CMAKE_CURRENT_LIST_DIR}/boost_multi_index-targets.cmake\")
")

write_basic_package_version_file("${PROJECT_BINARY_DIR}/boost_multi_index-config-version.cmake"
  VERSION 1.64
  COMPATIBILITY AnyNewerVersion
  )

install(FILES
    "${PROJECT_BINARY_DIR}/boost_multi_index-config.cmake"
    "${PROJECT_BINARY_DIR}/boost_multi_index-config-version.cmake"
  DESTINATION lib/cmake/boost_multi_index
)

