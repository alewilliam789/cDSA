file_header = -isystem./include
library_headers = -isystem../lib/include
libraries_path = -L../lib
libraries =
library_build_path = ../lib/


test : hash.c hash.test.c 
	gcc $(file_header) $(library_headers) -Wall -pedantic -Werror -Wextra -g hash.c hash.test.c $(libraries_path) $(libraries)

library : hash.c
	- rm ../lib/libhash.so
	gcc $(file_header) $(library_headers) -c -Wall -pedantic -Werror -Wextra -fPIC hash.c $(libraries_path) $(libraries)
	gcc -shared -o libhash.so hash.o
	- rm hash.o
	mv ./libhash.so $(library_build_path)
	cp ./include/hash.h $(library_build_path)/include

json : hash.c hash.test.c
	- rm compile_commands.json
	bear -- make test
	- rm -r a.out

debug : a.out
	gdb a.out

clean : 
	- rm a.out

