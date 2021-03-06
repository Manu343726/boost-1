cmake_minimum_required(VERSION 3.5)
project(boost_xpressive)

find_package(BCM)
include(BCMDeploy)
include(BCMSetupVersion)

find_package(boost_iterator)
find_package(boost_utility)
find_package(boost_static_assert)
find_package(boost_proto)
find_package(boost_type_traits)
find_package(boost_smart_ptr)
find_package(boost_config)
find_package(boost_numeric_conversion)
find_package(boost_core)
find_package(boost_mpl)
find_package(boost_conversion)
find_package(boost_assert)
find_package(boost_fusion)
find_package(boost_preprocessor)
find_package(boost_integer)
find_package(boost_optional)
find_package(boost_exception)
find_package(boost_range)
find_package(boost_typeof)
find_package(boost_lexical_cast)
find_package(boost_throw_exception)

bcm_setup_version(VERSION 1.64.0)

add_library(boost_xpressive INTERFACE
)
set_property(TARGET boost_xpressive PROPERTY EXPORT_NAME xpressive)

target_link_libraries(boost_xpressive INTERFACE boost::iterator)
target_link_libraries(boost_xpressive INTERFACE boost::utility)
target_link_libraries(boost_xpressive INTERFACE boost::static_assert)
target_link_libraries(boost_xpressive INTERFACE boost::proto)
target_link_libraries(boost_xpressive INTERFACE boost::type_traits)
target_link_libraries(boost_xpressive INTERFACE boost::smart_ptr)
target_link_libraries(boost_xpressive INTERFACE boost::config)
target_link_libraries(boost_xpressive INTERFACE boost::numeric_conversion)
target_link_libraries(boost_xpressive INTERFACE boost::core)
target_link_libraries(boost_xpressive INTERFACE boost::mpl)
target_link_libraries(boost_xpressive INTERFACE boost::conversion)
target_link_libraries(boost_xpressive INTERFACE boost::assert)
target_link_libraries(boost_xpressive INTERFACE boost::fusion)
target_link_libraries(boost_xpressive INTERFACE boost::preprocessor)
target_link_libraries(boost_xpressive INTERFACE boost::integer)
target_link_libraries(boost_xpressive INTERFACE boost::optional)
target_link_libraries(boost_xpressive INTERFACE boost::exception)
target_link_libraries(boost_xpressive INTERFACE boost::range)
target_link_libraries(boost_xpressive INTERFACE boost::typeof)
target_link_libraries(boost_xpressive INTERFACE boost::lexical_cast)
target_link_libraries(boost_xpressive INTERFACE boost::throw_exception)




bcm_deploy(TARGETS boost_xpressive INCLUDE include NAMESPACE boost::)

if(BOOST_CMAKE_BUILD_TESTS)
    add_subdirectory(test)
endif()
