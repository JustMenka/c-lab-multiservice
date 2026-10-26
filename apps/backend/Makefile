CC ?= gcc
CFLAGS ?= -O2 -Wall -Wextra

INCLUDE_DIR = ../../include
LIB_DIR = ../../build/lib

all: backend

main.o: main.c handler.h
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c main.c -o main.o

handler.o: handler.c handler.h
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c handler.c -o handler.o

backend: main.o handler.o $(LIB_DIR)/libcommon.a
	$(CC) $(CFLAGS) main.o handler.o $(LIB_DIR)/libcommon.a -o backend

clean:
	rm -f backend main.o handler.o

.PHONY: all clean	

