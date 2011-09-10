CC := gcc					#compiler
SRC := $(wildcard src/*.c)			#source files
OBJ := $(patsubst src/%.c,obj/%.o,$(SRC))	#object files
LFLAGS :=					#linking flags
CFLAGS :=					#compiling flags

main.exe: $(OBJ)
	$(CC) $(LFLAGS) -o $@ $<

obj/%.o: src/%.c
	$(CC) $(CFLAGS) -c -o $@ $<

clean:
	rm $(OBJ)