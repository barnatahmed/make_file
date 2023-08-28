

#all : 
#	gcc -c main.c -o main.o
#	gcc -c lib.c -o lib.o
#	gcc lib.o main.o -o main

DEBUG = 1
EXECUTABLE = main

SRC_LOC = Src
OBJ_LOC = Build

CC_STANDARD = c90
CC_WARNINGS = -Wall -Wextra -Wpedantic
CC = gcc
CXX = g++
CFLAGS = $(CC_WARNINGS) -std=$(CC_STANDARD) $(LDFLAGS)
LDFLAGS = -I Inc

ifeq ($(DEBUG) , 1)
CFLAGS += -g -O0
else
CFLAGS += -O3
endif

COMPILER = $(CC) $(CFLAGS) $(LDFLAGS)

#SOURCES = lib.c main.c
SOURCES = $(wildcard $(SRC_LOC)/*.c)
OBJECTS = $(patsubst $(SRC_LOC)/%.c, $(OBJ_LOC)/%.o, $(SOURCES))  # replace every *.c with *.o from the list named SOURCES

#OBJECTS = $(wildcard *.o) ( you can't use it because initialy they don't exist)  !!!!!!!!!!!!!!!
#OBJECTS = lib.o main.o


all : create $(OBJECTS)
	echo $(SOURCES)
	$(COMPILER) $(OBJECTS) -o $(EXECUTABLE)

# -p : if the folder already exists, don't create it
# @: don't display the command in the output console
create:
	@mkdir -p $(OBJ_LOC) 

# $@: the file name of the target
# $<: the name of the first dep
# $^: the names of all prerequisties

# % : means innovate the command one by one 

$(OBJ_LOC)/%.o : $(SRC_LOC)/%.c
	$(COMPILER) -c $< -o $@

execute: 
	./$(EXECUTABLE)

clean:
	rm -f $(EXECUTABLE) $(SRC_LOC)/*.o
	rm -r $(OBJ_LOC)


# phony are the targets that aren't file names ( used to prevent confusions to the reader and facilitate things to the "parser")
.PHONY : clean execute create all