DIR_INC = ../code/include
DIR_SRC = ../code/src
DIR_OBJ = temp
DIR_BIN = final

SRC = $(wildcard ${DIR_SRC}/*.c)  
OBJ = $(patsubst %.c,${DIR_OBJ}/%.o,$(notdir ${SRC})) 

TARGET = main

BIN_TARGET = ${DIR_BIN}/${TARGET}

CC = gcc
CFLAGS = -g -Wall -O2 -I${DIR_INC}

${BIN_TARGET}:${OBJ}
ifneq ($(DIR_BIN), $(wildcard $(DIR_BIN)))
	mkdir $(DIR_BIN)
endif
	$(CC) $(OBJ)  -o $@
		    
${DIR_OBJ}/%.o:${DIR_SRC}/%.c
ifneq ($(DIR_OBJ), $(wildcard $(DIR_OBJ)))
	mkdir $(DIR_OBJ)
endif
	$(CC) $(CFLAGS) -c  $< -o $@

.PHONY:clean

clean:
	rm -rf $(DIR_OBJ)
	rm -rf $(DIR_BIN)
