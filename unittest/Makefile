BTEST_DIR=../../../btest

CXXFLAGS=-g -O0

INCPATH= -I$(BTEST_DIR)/gtest/output/include \
		 -I../output/

DEP_LDFLAGS= -L$(BTEST_DIR)/gtest/output/lib \
			 -L../output/

DEP_LDLIBS= -lgtest -lgtest_main -ldict_parser -lpthread
#DEP_LDLIBS= /usr/lib/libgtest.a /usr/lib/libgtest_main.a -ldict_parser -lpthread

CXX=g++

PATTERN=test*.cpp
TESTFILES=$(wildcard $(PATTERN))
EXE=$(basename $(TESTFILES))
all : $(EXE) output
$(EXE) : % : %.cpp
	$(CXX) $^ -o $@ $(CXXFLAGS) $(INCPATH) $(DEP_LDFLAGS) $(DEP_LDLIBS)
.PHONY: list clean output
list:
	@echo $(EXE)

output:
	rm -rf ./output
	mkdir ./output
	mv $(EXE) ./output/

clean:
	rm -rf ./output
	rm -f $(EXE)
