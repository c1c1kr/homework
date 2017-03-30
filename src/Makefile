# Makefile sample

CC=gcc
CFLAGS= -g $(INCLUDE) -fPIC
CFLAGS1=-c -g 
INCLUDE=-I../inc
LIBS=-L./ -lmyio

SRCS=main.c read.c write.c
OBJS=$(SRCS:.c=.o)

TARGET=libmyio.so.0

.SUFFIXES:.c.o
.c.o:
	$(CC) $(CFLAGS1) $(INCLUDE) $<

all: $(TARGET) link test  

$(TARGET):$(OBJS)
	$(CC) -shared -Wl,-soname,$@ -o $@ $(OBJS)
link:
	ln -sf $(TARGET) $(TARGET:.so.0=.so)
test: main.o $(TARGET)
	$(CC) -o $@ main.o $(LIBS)
	@echo done
dep:
	gccmakedep $(INCLUDE) $(SRCS)
clean:
	rm -rf $(OBJS) $(TARGET) $(TARGET:.so.0=.so) test core
