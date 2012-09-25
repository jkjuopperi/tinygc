#
# TinyGC
# https://tinygc.svn.sourceforge.net/svnroot/tinygc
#

cmake_minimum_required(VERSION 2.6)
project(tosiboxd C)
set(tinygc_MAJOR_VERSION 2)
set(tinygc_MINOR_VERSION 6)

set(tinygc_SOURCES
	tinygc.c
	)

set(tinygc_HEADERS
	gc_gcj.h
	gc_mark.h
	javaxfc.h
	)

set(tinygc_PUBLIC_HEADERS
	gc.h
	)

add_library(tinygc SHARED
	${tinygc_SOURCES}
	${tinygc_HEADERS}
	${tinygc_PUBLIC_HEADERS}
	)

set_target_properties(tinygc PROPERTIES
	VERSION ${tinygc_MAJOR_VERSION}.${tinygc_MINOR_VERSION}
	SOVERSION ${tinygc_MAJOR_VERSION}.${tinygc_MINOR_VERSION}
	PUBLIC_HEADER "${tinygc_PUBLIC_HEADERS}"
	)

install(TARGETS tinygc
	LIBRARY DESTINATION "lib"
	PUBLIC_HEADER DESTINATION "include"
	)
