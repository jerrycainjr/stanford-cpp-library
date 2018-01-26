# CS106B/X Libraries
CXX = g++

LIB_SRC = \
	process.cpp \
	thread.cpp \
	call_stack_gcc.cpp \
	error.cpp \
	exceptions.cpp

WARNINGS = -Wall -pedantic -Wno-unused-function -Wno-vla -Wno-vla-extension
DEPS = -MMD -MF $(@:.o=.d)
DEFINES = 
INCLUDES = -I. -I.. -I../io -I../util -I../graphics -I../collections

CXXFLAGS = -g $(WARNINGS) -O0 -std=c++0x $(DEFINES) $(INCLUDES)
LDFLAGS = 

LIB_OBJ = $(patsubst %.cpp,%.o,$(patsubst %.S,%.o,$(LIB_SRC)))
LIB_DEP = $(patsubst %.o,%.d,$(LIB_OBJ))
LIB = cs106lib_system.a

default: $(LIB)

$(LIB): $(LIB_OBJ)
	@rm -f $@
	@ar r $@ $^
	@ranlib $@

clean::
	@rm -f $(LIB) $(LIB_DEP) $(LIB_OBJ)

spartan:: clean
	@rm -fr *~

.PHONY: all clean spartan

-include $(LIB_DEP)

