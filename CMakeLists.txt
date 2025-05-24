cmake_minimum_required(VERSION 3.10)
project(lab06 VERSION 1.0.0)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(formatter_lib)
add_subdirectory(formatter_ex_lib)
add_subdirectory(solver_lib)
add_subdirectory(hello_world_application)
add_subdirectory(solver_application)

install(TARGETS solver_application hello_world_application
        RUNTIME DESTINATION bin)

set(CPACK_PACKAGE_NAME "solver")
set(CPACK_PACKAGE_VERSION ${PROJECT_VERSION})
set(CPACK_PACKAGE_VENDOR "neddsr")
set(CPACK_RESOURCE_FILE_LICENSE "${CMAKE_SOURCE_DIR}/LICENSE.txt")

if(WIN32)
  string(UUID CPACK_WIX_PRODUCT_GUID NAMESPACE "00000000-0000-0000-0000-000000000000" 
         NAME "MyProduct" TYPE SHA1 UPPER)
  string(UUID CPACK_WIX_UPGRADE_GUID NAMESPACE "00000000-0000-0000-0000-000000000000" 
         NAME "MyProductUpgrade" TYPE SHA1 UPPER)
  set(CPACK_WIX_ARCHITECTURE "x64")
endif()

include(CPack)
