

#all : 
#	gcc -c main.c -o main.o
#	gcc -c lib.c -o lib.o
#	gcc lib.o main.o -o main

SRC_LOC = src

DEBUG = 1
EXECUTABLE = main

CC_STANDARD = c90
CC_WARNINGS = -Wall -Wextra -Wpedantic
CC = gcc
CXX = g++
CFLAGS = $(CC_WARNINGS) -std=$(CC_STANDARD)
LDFLAGS = -l include


ifeq ($(DEBUG) , 1)


COMPILER = $(CC) $(CFLAGS)
CFLAGS += -g -O0
else
CFLAGS += -O3
endif



all : lib.o main.o 
	echo $(COMPILER)
	$(COMPILER) lib.o main.o -o $(EXECUTABLE)

lib.o: 
	$(COMPILER) -c lib.c -o lib.o

main.o : 
	$(COMPILER) -c main.c -o main.o

execute: 
	./$(EXECUTABLE)

clean:
	rm -f $(EXECUTABLE) *.o