.PHONY: bidl2sl

VERSION = \"2.2.4.0\"
#CC = g++
CFLAGS = -Wall -W -pipe -Wno-unused -Wreorder -Wwrite-strings -Wswitch -Wno-sign-compare \
		 -finline-functions -Winline -Wreturn-type -Wtrigraphs -Wformat -Wparentheses -Wpointer-arith -Werror \
		 -g3 -DVERSION=$(VERSION) -D_BIDL_DEBUG=1
EXE = bidl2sl

SRC_DIR= .
INC = -I.

SOURCES = $(wildcard $(SRC_DIR)/*.cpp)
OBJS = $(patsubst %.cpp,%.o,$(SOURCES))

SCANNER = scaner
GRAMMAR = grammar

$(EXE): $(OBJS)
	#$(EXE): $(GRAMMAR).y $(SCANNER).l $(OBJS)
	#bison -d $(GRAMMAR).y
	#flex -o$(SCANNER).c $(SCANNER).l
	$(CXX) -o $@ $(OBJS) $(CFLAGS)

$(OBJS): %.o: %.cpp 
	$(CXX) $(CFLAGS) -c $< -o $@ $(INC_PATH)

clean:
	rm -rf $(EXE) $(OBJS)
