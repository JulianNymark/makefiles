#compiles all the source files! (from src/ to obj/)
#links all the objects! (into program)
CC := msp430-gcc
SRC := $(wildcard src/*.c)
OBJ := $(patsubst src/%.c,obj/%.o,$(SRC))
LFLAGS := -mmcu=msp430x2012
CFLAGS := -Os -Wall -mmcu=msp430x2012


all: program

debug : CFLAGS += -DDEBUG -g
debug : program

obj/%.o : src/%.c
	$(CC) $(CFLAGS) -o $@ -c $<

program : $(OBJ)
	$(CC) $(LFLAGS) -o $@ $^

.PHONY : clean
clean :
	rm program $(OBJ)