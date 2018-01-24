# CS106B/X Libraries
CXX = g++

WARNINGS = -Wall -pedantic -Wno-unused-function -Wno-vla
DEPS = -MMD -MF $(@:.o=.d)
DEFINES = 
INCLUDES = 

CXXFLAGS = -g $(WARNINGS) -O0 -std=c++0x $(DEFINES) $(INCLUDES)
LDFLAGS = 

LIB_OBJ = $(patsubst %.cpp,%.o,$(patsubst %.S,%.o,$(LIB_SRC)))
LIB_DEP = $(patsubst %.o,%.d,$(LIB_OBJ))
LIB = cs106bx.a

default: $(LIB)

$(LIB): $(LIB_OBJ)
	rm -f $@
	ar r $@ $^
	ranlib $@

clean::
	rm -f $(LIB) $(LIB_DEP) $(LIB_OBJ)

spartan:: clean
	\rm -fr *~

.PHONY: all clean spartan

-include $(LIB_DEP)

