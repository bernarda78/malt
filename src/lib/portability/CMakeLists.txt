############################################################
#    PROJECT  : MALT (MALoc Tracker)
#    VERSION  : 1.2.4
#    DATE     : 10/2024
#    LICENSE  : CeCILL-C
#    FILE     : src/lib/portability/CMakeLists.txt
#-----------------------------------------------------------
#    AUTHOR   : Sébastien Valat (ECR) - 2014 - 2015
#    AUTHOR   : Sébastien Valat - 2019
############################################################

############################################################
if (MALT_PORTABILITY_OS_UNIX)
	list(APPEND MALT_PORT_SRC OSUnix.cpp)
endif (MALT_PORTABILITY_OS_UNIX)

############################################################
list(APPEND MALT_PORT_SRC LinuxProcMapReader.cpp)
list(APPEND MALT_PORT_SRC CompilerGNU.cpp)

############################################################
add_library(malt-port OBJECT ${MALT_PORT_SRC})
SET_TARGET_PROPERTIES(malt-port PROPERTIES COMPILE_FLAGS -fPIC)

############################################################
if (ENABLE_TESTS)
	add_subdirectory(tests)
endif (ENABLE_TESTS)