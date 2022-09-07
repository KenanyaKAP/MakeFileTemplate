CXX=gcc
CXXFLAGS+= -std=c11 -O3 -Wall -Wextra -I.

OUTPUT=main

SOURCEDIR=src
OBJECTSDIR=obj

SOURCES=$(wildcard $(SOURCEDIR)/*.c)
OBJECTS=$(SOURCES:$(SOURCEDIR)/%.c=$(OBJECTSDIR)/%.o)

$(OUTPUT): $(OBJECTS)
	$(CXX) $^ $(CXXFLAGS) -o $@

$(OBJECTSDIR)/%.o: $(SOURCEDIR)/%.c
	$(CXX) $< $(CXXFLAGS) -c -o $@

$(OBJECTS): | $(OBJECTSDIR)

$(OBJECTSDIR):
	mkdir $@

clean:
	del $(OBJECTSDIR)\*.o $(OUTPUT).exe

%.exe: %.c
	$(CXX) $< $(CXXFLAGS) -o $@