# CS106B/X Libraries
CXX = g++

LIB_SRC = \
	strlib.cpp \
	biginteger.cpp \
	complex.cpp \
	timer.cpp \
	random.cpp \
	point.cpp \
	recursion.cpp \
	gmath.cpp \
	direction.cpp

WARNINGS = -Wall -pedantic -Wno-unused-function -Wno-vla
DEPS = -MMD -MF $(@:.o=.d)
DEFINES = 
INCLUDES = -I.. -I../system -I../collections -I../graphics -I../io

CXXFLAGS = -g $(WARNINGS) -O0 -std=c++0x $(DEFINES) $(INCLUDES)
LDFLAGS = 

LIB_OBJ = $(patsubst %.cpp,%.o,$(patsubst %.S,%.o,$(LIB_SRC)))
LIB_DEP = $(patsubst %.o,%.d,$(LIB_OBJ))
LIB = cs106lib_util.a

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

