file_header = -isystem./include
library_headers = -isystem../lib/include
libraries_path = -L../lib
libraries = -larena
library_build_path = ../lib/


test : linkedlist.c linkedlist.test.c 
	gcc $(file_header) $(library_headers) -Wall -pedantic -Werror -Wextra -g linkedlist.c linkedlist.test.c $(libraries_path) $(libraries)

library : linkedlist.c
	- rm ../lib/liblinkedlist.so
	gcc $(file_header) $(library_headers) -c -Wall -pedantic -Werror -Wextra -fPIC linkedlist.c $(libraries_path) $(libraries)
	gcc -shared -o liblinkedlist.so linkedlist.o
	- rm linkedlist.o
	mv ./liblinkedlist.so $(library_build_path)
	cp ./include/linkedlist.h $(library_build_path)/include

json : linkedlist.c linkedlist.test.c
	- rm compile_commands.json
	bear -- make test
	- rm -r a.out

debug : a.out
	gdb a.out

clean : 
	- rm a.out

