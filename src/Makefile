# Makefile sample

CC=gcc
AR=ar
CFLAGS= -g $(INCLUDE) -fPIC
CFLAGS1=-c -g 
INCLUDE=-I../inc
LIBS=-L./ -lmyio

SRCS=read.c write.c
OBJS=$(SRCS:.c=.o)

TARGET=libmyio.so.0

.SUFFIXES:.c.o
.c.o:
	$(CC) $(CFLAGS1) $(INCLUDE) $<

all: $(TARGET) test

$(TARGET):$(OBJS)
	$(CC) -shared -Wl,-soname,$@ -o $@ $(OBJS)
test: main.o $(TARGET)
	$(CC) -o $@ main.o $(LIBS)
	@echo done
dep:
	gccmakedep $(INCLUDE) $(SRCS)
clean:
	rm -rf $(OBJS) $(TARGET) core
