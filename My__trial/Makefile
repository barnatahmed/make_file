

SRC_FOLDER = ./Src
OBJ_FOLDER = ./Obj
EXE_FOLDER = ./exe

DEBUG = 1

CC = gcc
EXECUTABLE = main

FLAGS = -Wall -Wextra -Wpedantic -std=c99
INCLUDES = -I Inc

ifeq ($(DEBUG),1)
FLAGS += -g -O0
else
FLAGS += O3
endif

SRC_FILES = $(wildcard $(SRC_FOLDER)/*.c )
OBJ_FILES = $(patsubst $(SRC_FOLDER)/%.c, $(OBJ_FOLDER)/%.o ,$(SRC_FILES))

COMPILER = $(CC) $(FLAGS) $(INCLUDES) 


all : prepare $(OBJ_FILES)
	echo $(OBJ_FILES)
	$(COMPILER) $(OBJ_FILES) -o $(EXE_FOLDER)/$(EXECUTABLE)

prepare :
	mkdir -p $(OBJ_FOLDER) $(EXE_FOLDER)

$(OBJ_FOLDER)/%.o : $(SRC_FOLDER)/%.c
	$(COMPILER) -c $< -o $@

execute:
	$(EXE_FOLDER)/$(EXECUTABLE)

clean:
	rm -f $(OBJ_FOLDER)/*.o $(EXE_FOLDER)/$(EXECUTABLE)
	rmdir $(OBJ_FOLDER) $(EXE_FOLDER)

.PHONY : clean prepare all execute