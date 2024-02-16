file_header = -isystem./include
library_headers = -isystem../lib/include
libraries_path = -L../lib
libraries = -larena
library_build_path = ../lib/


binary-test : binarytree.c binarytree.test.c 
	gcc $(file_header) $(library_headers) -Wall -pedantic -Werror -Wextra -g binarytree.c binarytree.test.c $(libraries_path) $(libraries)

binary-library : binarytree.c
	- rm ../lib/libbinarytree.so
	gcc $(file_header) $(library_headers) -c -Wall -pedantic -Werror -Wextra -fPIC binarytree.c $(libraries_path) $(libraries)
	gcc -shared -o libbinarytree.so binarytree.o
	- rm binarytree.o
	mv ./libbinarytree.so $(library_build_path)
	cp ./include/tree.h $(library_build_path)/include

binary-json : binarytree.c binarytree.test.c
	- rm compile_commands.json
	bear -- make test
	- rm -r a.out

debug : a.out
	gdb a.out

clean : 
	- rm a.out
