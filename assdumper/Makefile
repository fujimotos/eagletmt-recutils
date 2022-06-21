CXX = g++
CXXFLAGS = -O2 -Wall -W
LDFLAGS =
TARGET = assdumper tsvdumper

all: $(TARGET)

%: %.cc
	$(CXX) $(CXXFLAGS) $(LDFLAGS) $< -o $@

clean:
	$(RM) $(TARGET)

.PHONY: all clean

