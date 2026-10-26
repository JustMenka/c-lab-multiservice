CC ?= gcc
CFLAGS ?= -O2 -Wall -Wextra


INCLUDE_DIR = ../../include
LIB_DIR = ../../build/lib

all: loadgen

main.o: main.c stats.h
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c main.c -o main.o

stats.o: stats.c stats.h
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c stats.c -o stats.o

loadgen: main.o stats.o $(LIB_DIR)/libcommon.a
	$(CC) $(CFLAGS) main.o stats.o $(LIB_DIR)/libcommon.a -o loadgen

clean:
	rm -f stats.o main.o loadgen

.PHONY: all clean
