GET_FILENAME_COMPONENT(OBJNAME ${CMAKE_CURRENT_LIST_DIR} NAME)
AUX_SOURCE_DIRECTORY(. OBJECT_SRC)
ADD_LIBRARY(${OBJNAME} OBJECT ${OBJECT_SRC})
SOURCE_GROUP(${OBJNAME} FILES ${OBJECT_SRC})
