
ifndef CPPC
	CPPC=g++
endif

CPP_COMMON = ../../Cpp_common

INC_DIR = /usr/local/cuda/include/CL
LIB_DIR = /usr/local/cuda/lib64


CCFLAGS=

INC = -I $(CPP_COMMON)

LIBS = -lOpenCL

# Check our platform and make sure we define the APPLE variable
# and set up the right compiler flags and libraries
PLATFORM = $(shell uname -s)
ifeq ($(PLATFORM), Darwin)
	CPPC = clang++
	LIBS = -framework OpenCL
endif

DeviceInfo: DeviceInfo.cpp
	$(CPPC) $^ $(INC) -I $(INC_DIR)  $(CCFLAGS) -L $(LIB_DIR) $(LIBS) -o $@


clean:
	rm -f DeviceInfo
