if(MSVC)
    # Disable some overly strict MSVC warnings.
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -wd4244 -wd4800 -wd4805")
endif()

set(intern_HEADERS
    intern/drw_cptable932.h
    intern/drw_cptable936.h
    intern/drw_cptable949.h
    intern/drw_cptable950.h
    intern/drw_cptables.h
    intern/drw_dbg.h
    intern/drw_textcodec.h
    intern/dwgbuffer.h
    intern/dwgreader15.h
    intern/dwgreader18.h
    intern/dwgreader21.h
    intern/dwgreader24.h
    intern/dwgreader27.h
    intern/dwgreader.h
    intern/dwgutil.h
    intern/dxfreader.h
    intern/dxfwriter.h
    intern/rscodec.h)

set(intern_SOURCES
    intern/drw_dbg.cpp
    intern/drw_textcodec.cpp
    intern/dwgbuffer.cpp
    intern/dwgreader15.cpp
    intern/dwgreader18.cpp
    intern/dwgreader21.cpp
    intern/dwgreader24.cpp
    intern/dwgreader27.cpp
    intern/dwgreader.cpp
    intern/dwgutil.cpp
    intern/dxfreader.cpp
    intern/dxfwriter.cpp
    intern/rscodec.cpp)

set(libdxfrw_HEADERS
    drw_base.h
    drw_interface.h
    drw_header.h
    drw_classes.h
    drw_entities.h
    drw_objects.h
    libdxfrw.h)

set(libdxfrw_SOURCES
    drw_header.cpp
    drw_classes.cpp
    drw_entities.cpp
    drw_objects.cpp
    libdxfrw.cpp)

set(libdwgr_HEADERS
    libdwgr.h)

set(libdwgr_SOURCES
    libdwgr.cpp)

add_library(dxfrw STATIC
    ${intern_HEADERS}
    ${intern_SOURCES}
    ${libdxfrw_HEADERS}
    ${libdxfrw_SOURCES}
    ${libdwgr_HEADERS}
    ${libdwgr_SOURCES})

target_include_directories(dxfrw PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/intern/)

target_include_directories(dxfrw PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/)
