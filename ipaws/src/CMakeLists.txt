# configure a header file to pass some of the CMake settings
# to the source code
#configure_file (
#  "config.h.in"
#  "config.h"
#  )

# add the binary tree to the search path for include files
# so that we will find TutorialConfig.h

# add the executable
link_directories(
  ${GLIB_LIBRARY_DIRS}  ${GSOAP_LIBRARY_DIRS}  ${STROPHE_LIBRARY_DIRS})

include_directories(
  ${GLIB_INCLUDE_DIRS}  ${GSOAP_INCLUDE_DIRS}  ${STROPHE_INCLUDE_DIRS})

add_executable(stormee-bridge main.c plugin.c soapC.c soapClient.c smdevp.c mecevp.c wsseapi.c threads.c ipaws.c xmpp.c)

target_link_libraries(stormee-bridge 
  ${GLIB_LIBRARIES}  ${GSOAP_LIBRARIES} ${STROPHE_LIBRARIES})
