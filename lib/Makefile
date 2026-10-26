CC ?= gcc
CFLAGS = -O2 -Wall -Wextra

INCLUDE_DIR = ../include
LIB_DIR = ../build/lib

all: $(LIB_DIR)/libcommon.a

net.o: net.c
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c net.c -o net.o

http.o: http.c
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c http.c -o http.o

utils.o: utils.c 
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c utils.c -o utils.o

$(LIB_DIR)/libcommon.a: net.o http.o utils.o
	mkdir -p $(LIB_DIR)
	ar rcs $(LIB_DIR)/libcommon.a net.o http.o utils.o

clean:
	rm -rf net.o http.o utils.o
	rm -rf $(LIB_DIR)/libcommon.a

.PHONY: all clean
