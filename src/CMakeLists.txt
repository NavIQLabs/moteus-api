add_library(moteus_api SHARED
  moteus_api.cpp
)

target_compile_features(moteus_api PUBLIC cxx_std_20)

target_include_directories(moteus_api SYSTEM PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../include/moteus_drivers>
)

target_include_directories(moteus_api PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../include/moteus_api>
  $<INSTALL_INTERFACE:include>
)

install(TARGETS moteus_api 
  ARCHIVE DESTINATION lib
  LIBRARY DESTINATION lib
  RUNTIME DESTINATION bin
)  
