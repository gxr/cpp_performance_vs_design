SRCFILES=$(wildcard *.cpp)
TARGETS=$(patsubst %.cpp,%,$(SRCFILES))

ifeq ($(CXXFLAGS),)
ifeq ($(CXX),g++)
CXXFLAGS=-O2 -march=native -ftree-vectorize -ffast-math
endif

ifeq ($(CXX),clang++)
CXXFLAGS+=-O2 -march=native
endif

ifeq ($(CXX),icpc)
CXXFLAGS+=-O2 -xHost 
endif
endif

all : $(TARGETS)

$(TARGETS) : % : %.cpp
	$(CXX) $(CXXFLAGS) $< -o $@

clean :
	rm -vf $(TARGETS) 
