PROG := xcrun

CFLAGS :=
LFLAGS :=

CC := $(shell which clang)

#CFLAGS += \
	-Wall \
	-Werror

C_SRCS := \
	ini.c \
	xcrun.c

OBJS := \
	$(patsubst %.c,%.o, $(filter %.c,$(C_SRCS)))

%.c.o:
	$(CC) -x c $(CFLAGS) -c $< -o $@

all: $(OBJS)
	$(CC) $(OBJS) -o $(PROG) $(LFLAGS)

install: all
	install -d $(DESTDIR)/usr/bin
	install -s -m 755 $(PROG) $(DESTDIR)/usr/bin/$(PROG)

clean:
	rm -f $(OBJS) $(PROG)
