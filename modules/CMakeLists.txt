# Add all modules
ADD_SUBDIRECTORY(backgroundactivityfilter)
ADD_SUBDIRECTORY(cameracalibration)
ADD_SUBDIRECTORY(frameenhancer)
ADD_SUBDIRECTORY(framestatistics)
ADD_SUBDIRECTORY(ini)
ADD_SUBDIRECTORY(misc)
ADD_SUBDIRECTORY(statistics)
ADD_SUBDIRECTORY(visualizer)
ADD_SUBDIRECTORY(meanratefilter)
ADD_SUBDIRECTORY(synapsereconfig)
ADD_SUBDIRECTORY(fpgaspikegen)
ADD_SUBDIRECTORY(softspikegen)
ADD_SUBDIRECTORY(poissonspikegen)
ADD_SUBDIRECTORY(reservoir)
ADD_SUBDIRECTORY(netparser)
ADD_SUBDIRECTORY(nullhopinterface)
ADD_SUBDIRECTORY(arduinocnt)

# Support private modules that don't get considered for commit,
# by reserving a directory called PrivateModules with its own
# CMake PrivateModules.txt, and ignoring it.
INCLUDE(PrivateModules/PrivateModules.txt OPTIONAL)
