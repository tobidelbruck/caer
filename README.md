# caer


AER event-based framework, written in C, targeting embedded systems.<br />
[![Build Status](https://travis-ci.org/inilabs/caer.svg?branch=master)](https://travis-ci.org/inilabs/caer)

# Dependencies:

Linux, MacOS X or Windows (for Windows build instructions see README.Windows) <br />
gcc >= 5.2 or clang >= 3.6 <br />
cmake >= 2.6 <br />
Boost >= 1.50 (with system, filesystem, iostreams, program_options) <br />
libcaer >= 2.4.0 <br />
Optional: tcmalloc >= 2.2 (faster memory allocation) <br />
Optional: SFML >= 2.3.0 (visualizer module) <br />
Optional: OpenCV >= 3.1 (cameracalibration, poseestimation modules) <br />
Optional: libpng >= 1.6 (input/output frame PNG compression) <br />
Optional: libuv >= 1.7.5 (output module) <br />

# Installation

1) configure: <br />

$ cmake <OPTIONS> <MODULES_TO_BUILD> . <br />

The following options are currently supported: <br />
-DUSE_TCMALLOC=1 -- Enables usage of TCMalloc from Google to allocate memory. <br />

The following modules can currently be selected to be built: <br />
-DDVS128=1 -- DVS128 device input. <br />
-DEDVS=1 -- eDVS4337 device input. <br />
-DDAVIS=1 -- DAVIS device input. <br />
-DDYNAPSE=1 -- Dynap-se device input (neuromorphic chip). <br />
-DBAFILTER=1 -- Filter background activity (uncorrelated noise). <br />
-DFRAMEENHANCER=1 -- Demosaic/enhance frames. <br />
-DCAMERACALIBRATION=1 -- Calculate and apply single camera lens calibration. <br />
-DSTATISTICS=1 -- Print statistics to console. <br />
-DVISUALIZER=1 -- Open windows in which to visualize data. <br />
-DINPUT_FILE=1 -- Get input from an AEDAT file. <br />
-DOUTPUT_FILE=1 -- Write data to an AEDAT 3.X file. <br />
-DINPUT_NETWORK=1 -- Read input from a network stream. <br />
-DOUTPUT_NETWORK=1 -- Send data out via network. <br />
-DROTATE=1 -- Rotate events. <br />
-DSYNAPSERECONFIG=1 -- Enable Davis240C to Dynap-se mapping  <br />
-DFPGASPIKEGEN=1 -- Enable FPGA spike generator Dynap-se <br />
-DPOISSONSPIKEGEN=1 -- Enable FPGA Poisson spike generator for Dynap-se <br />

To enable all just type: <br />
 cmake -DDVS128=1 -DEDVS=1 -DDAVIS=1 -DDYNAPSE=1 -DBAFILTER=1 -DFRAMEENHANCER=1 -DCAMERACALIBRATION=1 -DSTATISTICS=1  -DVISUALIZER=1 -DINPUT_FILE=1 -DOUTPUT_FILE=1 -DINPUT_NETWORK=1 -DOUTPUT_NETWORK=1 -DROTATE=1  -DMEANRATEFILTER=1 -DSYNAPSERECONFIG=1 -DFPGASPIKEGEN=1 -DPOISSONSPIKEGEN=1 .
<br />
2) build:
<br />
$ make
<br />
3) install:
<br />
$ make install
<br />
# Usage

You will need a 'caer-config.xml' file that specifies which and how modules
should be interconnected. A good starting point is 'docs/davis-config.xml', 
or 'docs/dynapse-config.xml', please also read through 'docs/modules.txt' for 
an explanation of the modules system and its configuration syntax.
<br />
$ caer-bin (see docs/ for more info on how to use cAER) <br />
$ caer-ctl (command-line run-time control program, optional) <br />

# Help

Please use our GitHub bug tracker to report issues and bugs, or
our Google Groups mailing list for discussions and announcements.

USER GUIDE: https://inilabs.com/support/software/caer/

BUG TRACKER: https://github.com/inilabs/caer/issues/

MAILING LIST: https://groups.google.com/d/forum/caer-users/

# Ubuntu 16.04, dependencies installation

On an Ubuntu 16.04, you can install all the dependencies (except libcaer) by typing: 
$ sudo apt-get install libboost-all-dev libboost-program-options1.58-dev libuv1-dev libsfml-dev libglew-dev gcc-5 g++-5 cmake
