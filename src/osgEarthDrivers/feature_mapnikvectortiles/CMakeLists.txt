FIND_PACKAGE(Protobuf)

IF(SQLITE3_FOUND AND Protobuf_FOUND AND Protobuf_PROTOC_EXECUTABLE)

INCLUDE_DIRECTORIES( ${SQLITE3_INCLUDE_DIR} ${CMAKE_CURRENT_BINARY_DIR})

SET(TARGET_SRC
    FeatureSourceMVT.cpp    
)

SET(TARGET_H
    MVTFeatureOptions
)

SET(TARGET_COMMON_LIBRARIES ${TARGET_COMMON_LIBRARIES} osgEarthFeatures osgEarthSymbology osgEarthUtil)
SET(TARGET_LIBRARIES_VARS SQLITE3_LIBRARY)
SETUP_PLUGIN(osgearth_feature_mapnikvectortiles)


# to install public driver includes:
SET(LIB_NAME feature_mapnikvectortiles)
SET(LIB_PUBLIC_HEADERS ${TARGET_H})
INCLUDE(ModuleInstallOsgEarthDriverIncludes OPTIONAL)

ENDIF()
