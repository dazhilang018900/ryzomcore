FILE(GLOB SRC *.cpp *.h ${RZ_SERVER_SRC_DIR}/ai_data_service/pacs_scan.h ${RZ_SERVER_SRC_DIR}/ai_data_service/pacs_scan.cpp *.rc)

SOURCE_GROUP("" FILES ${SRC})

ADD_EXECUTABLE(ai_build_wmap ${SRC})

INCLUDE_DIRECTORIES(${RZ_SERVER_SRC_DIR})

TARGET_LINK_LIBRARIES(ai_build_wmap
					ryzom_gameshare
					ryzom_aishare
					nelmisc)

NL_DEFAULT_PROPS(ai_build_wmap "Ryzom, Tools, Server: AI Build World Map")
NL_ADD_RUNTIME_FLAGS(ai_build_wmap)

INSTALL(TARGETS ai_build_wmap RUNTIME DESTINATION ${RYZOM_BIN_PREFIX} COMPONENT tools)
