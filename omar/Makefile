


# target : dependencies
#	command

DEBUG = 0
OBJ_FOLDER = ./Obj
SRC_FOLDER = ./Src
INC_FOLDER = ./Inc
EXE_FOLDER = ./Exe

CC = gcc
FLAGS = -Wextra -Wall -Wpedantic -std=c99 -I$(INC_FOLDER) -lmath

ifeq ($(DEBUG),1)
VERSION_TYPE = -g -O0
else
VERSION_TYPE = -O3
endif




COMPILER = $(CC) $(FLAGS) $(VERSION_TYPE)

ahmed: prepare $(OBJ_FOLDER)/main.o $(OBJ_FOLDER)/lib.o
	echo $(COMPILER)
	$(COMPILER) $(OBJ_FOLDER)/main.o $(OBJ_FOLDER)/lib.o -o $(EXE_FOLDER)/exe

prepare:
	@mkdir -p $(EXE_FOLDER) $(OBJ_FOLDER)

$(OBJ_FOLDER)/%.o : $(SRC_FOLDER)/%.c
	$(COMPILER) -c $< -o $@ 

execute:
	@$(EXE_FOLDER)/exe

clean:
	@rm -f $(OBJ_FOLDER)/*.o
	@rm $(EXE_FOLDER)/exe

.PHONY : clean execute prepare ahmed