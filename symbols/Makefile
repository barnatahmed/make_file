

#all : 
#	gcc -c main.c -o main.o
#	gcc -c lib.c -o lib.o
#	gcc lib.o main.o -o main

DEBUG = 1
EXECUTABLE = main

SRC_LOC = Src

CC_STANDARD = c90
CC_WARNINGS = -Wall -Wextra -Wpedantic
CC = gcc
CXX = g++
CFLAGS = $(CC_WARNINGS) -std=$(CC_STANDARD)


ifeq ($(DEBUG) , 1)


COMPILER = $(CC) $(CFLAGS) $(LDFLAGS)
CFLAGS += -g -O0
else
CFLAGS += -O3
endif

#SOURCES = lib.c main.c
SOURCES = $(wildcard *.c)
OBJECTS = $(patsubst %.c, %.o, $(SOURCES))  # replace every *.c with *.o from the list named SOURCES

#OBJECTS = $(wildcard *.o) ( you can't use it because initialy they don't exist)  !!!!!!!!!!!!!!!
#OBJECTS = lib.o main.o



all : $(OBJECTS) 
	echo $(SOURCES)
	$(COMPILER) $(OBJECTS) -o $(EXECUTABLE)

# $@: the file name of the target
# $<: the name of the first dep
# $^: the names of all prerequisties

%.o : %.c
	$(COMPILER) -c $< -o $@

execute: 
	./$(EXECUTABLE)

clean:
	rm -f $(EXECUTABLE) *.o