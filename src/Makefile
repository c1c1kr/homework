# Makefile sample

CC=gcc
AR=ar
CFLAGS= -g $(INCLUDE) -fPIC
INCLUDE=-I../inc
LIBS=-L./ -lmyio

SRCS=read.c write.c
OBJS=$(SRCS:.c=.o)

TARGET=libmyio.so.0
.SUFFIXES:.c.o
.c.o:
	$(CC) $(CFLAGS) $(INCLUDE) $<

all: $(TARGET)

$(TARGET):$(OBJS)
	$(CC) -shared -Wl,-soname,$@ -o $@ $(OBJS)

dep:
	gccmakedep $(INCLUDE) $(SRCS)
clean:
	rm -rf $(OBJS) $(TARGET) core
