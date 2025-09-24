CC=gcc
CFLAGS=-Wall

hello-makefile: main.o hello_fn.o
	$(CC) $(CFLAGS) -o hello-makefile main.o hello_fn.o

main.o: main.c hello.h
	$(CC) $(CFLAGS) -c main.c

hello_fn.o: hello_fn.c hello.h
	$(CC) $(CFLAGS) -c hello_fn.c

clean:
	rm -f main.o hello_fn.o hello-makefile
