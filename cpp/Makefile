#compiles all the source files! (from src/ to obj/)
#links all the objects! (into program)
CC := g++
LD := g++
SRC := $(wildcard src/*.cpp)
OBJ := $(patsubst src/%.cpp,obj/%.o,$(SRC))
SDL_LFLAGS := $(shell sdl-config --libs)
SDL_CFLAGS := $(shell sdl-config --cflags)
LFLAGS := $(SDL_LFLAGS)
CFLAGS := -Wall -I include $(SDL_CFLAGS)

all: program

debug : CFLAGS += -DDEBUG -g
debug : program

program : $(OBJ)
	$(LD) -o $@ $^ $(LFLAGS)

obj/%.o : src/%.cpp
	$(CC) -o $@ -c $< $(CFLAGS)

.PHONY : clean
clean :
	rm program $(OBJ)