#target: dep
#	Commands


all: 
	gcc -c main.c -o main.o
	gcc main.o -Wl,-Map="hello.map" -o main
execute: 
	./main

clean:
	rm -f main
	rm -f *.o
	rm -f *.map