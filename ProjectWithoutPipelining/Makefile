CC = gcc

CFLAGS = -g -std=c17 -D_POSIX_C_SOURCE=200809L \
		 -Wall -Werror -Wextra \
		 -Wcast-align -Wconversion -Wfloat-equal -Wformat=2 -Wnull-dereference -Wshadow -Wsign-conversion -Wswitch-enum -Wundef -Wunreachable-code -Wunused \
		 -fsanitize=address -fsanitize=undefined

ifneq ($(shell uname -s),Darwin) # if not MacOS
	CFLAGS += -fmax-errors=5
endif

all: ems jobs

ems: main.c constants.h operations.o parser.o eventlist.o threads.o
	$(CC) $(CFLAGS) $(SLEEP) -o ems main.c operations.o parser.o eventlist.o threads.o

%.o: %.c %.h
	$(CC) $(CFLAGS) -c ${@:.o=.c}

jobs:
	@mkdir -p jobs

run: ems
	@./ems

clean:
	rm -f *.o ems
	@if [ -d "jobs" ] && [ -z "$(shell ls -A jobs)" ]; then rm -rf jobs; else echo "Skipping non-empty jobs directory"; fi

format:
	@which clang-format >/dev/null 2>&1 || echo "Please install clang-format to run this command"
	clang-format -i *.c *.h
