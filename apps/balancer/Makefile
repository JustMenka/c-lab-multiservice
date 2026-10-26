CC ?= gcc
CFLAGS ?= -O2 -Wall -Wextra

INCLUDE_DIR=../../include
LIB_DIR = ../../build/lib

all: balancer

main.o: main.c router.h
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c main.c -o main.o

router.o: router.c router.h
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c router.c -o router.o
balancer: router.o main.o $(LIB_DIR)/libcommon.a
	$(CC) $(CFLAGS) main.o router.o $(LIB_DIR)/libcommon.a -o balancer

clean:
	rm -f main.o router.o balancer

.PHONY: all clean
