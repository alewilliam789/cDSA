file_header = -isystem./include
library_headers = -isystem../lib/include
libraries_path = -L../lib
libraries = -larena
library_build_path = ../lib/


test : heap.c heap.test.c 
	gcc $(file_header) $(library_headers) -Wall -pedantic -Werror -Wextra -g heap.c heap.test.c $(libraries_path) $(libraries)

library : heap.c
	- rm ../lib/libheap.so
	gcc $(file_header) $(library_headers) -c -Wall -pedantic -Werror -Wextra -fPIC heap.c $(libraries_path) $(libraries)
	gcc -shared -o libheap.so heap.o
	- rm heap.o
	mv ./libheap.so $(library_build_path)
	cp ./include/heap.h $(library_build_path)/include

json : heap.c heap.test.c
	- rm compile_commands.json
	bear -- make test
	- rm -r a.out

debug : a.out
	gdb a.out

clean : 
	- rm a.out


