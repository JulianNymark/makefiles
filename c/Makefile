#compiles all the source files! (from src/ to obj/)
#links all the objects! (into program)
CC := gcc
SRC := $(wildcard src/*.c)
OBJ := $(patsubst src/%.c,obj/%.o,$(SRC))
LFLAGS :=
CFLAGS := -Wall -I include

all: program

debug : CFLAGS += -DDEBUG -g
debug : program

program : $(OBJ)
	$(CC) $(LFLAGS) -o $@ $^

obj/%.o : src/%.c
	$(CC) $(CFLAGS) -o $@ -c $<

.PHONY : clean
clean :
	rm program $(OBJ)