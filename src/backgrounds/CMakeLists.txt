include_directories(${YAF_INCLUDE_DIRS})

add_definitions(-DBUILDING_YAFRAYPLUGIN)

add_library(sunsky SHARED sunsky.cc sunspectrum.cc)
target_link_libraries(sunsky yafaraycore)

add_library(textureback SHARED textureback.cc)
target_link_libraries(textureback yafaraycore)

add_library(gradientback SHARED gradientback.cc)
target_link_libraries(gradientback yafaraycore)

add_library(DarkSky SHARED DarkSky/darksky.cc)
target_link_libraries(DarkSky yafaraycore)

install (TARGETS gradientback textureback sunsky DarkSky ${YAF_TARGET_TYPE} DESTINATION ${YAF_PLUGIN_DIR})
