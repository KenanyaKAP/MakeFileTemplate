CXX=g++ 
CXXFLAGS+= -std=c++17 -O3 -Wall -Wextra -I. -lbgi -lgdi32 -lcomdlg32 -luuid -loleaut32 -lole32

OUTPUT=main

SOURCEDIR=src
OBJECTSDIR=obj

SOURCES=$(wildcard $(SOURCEDIR)/*.cpp)
OBJECTS=$(SOURCES:$(SOURCEDIR)/%.cpp=$(OBJECTSDIR)/%.o)

$(OUTPUT): $(OBJECTS)
	$(CXX) $^ $(CXXFLAGS) -o $@ 

$(OBJECTSDIR)/%.o: $(SOURCEDIR)/%.cpp
	$(CXX) $< $(CXXFLAGS) -c -o $@

$(OBJECTS): | $(OBJECTSDIR)

$(OBJECTSDIR):
	mkdir $@

clean:
	del $(OBJECTSDIR)\*.o $(OUTPUT).exe

%.exe: %.cpp
	$(CXX) $< $(CXXFLAGS) -o $@