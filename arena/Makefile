file_header = -isystem./include
library_headers = -isystem../lib/include
libraries_path = -L../lib
libraries =
library_build_path = ../lib/


test : arena.c arena.test.c 
	gcc $(file_header) $(library_headers) -Wall -pedantic -Werror -Wextra -g arena.c arena.test.c $(libraries_path) $(libraries)

library : arena.c
	- rm ../lib/libarena.so
	gcc $(file_header) $(library_headers) -c -Wall -pedantic -Werror -Wextra -fPIC arena.c $(libraries_path) $(libraries)
	gcc -shared -o libarena.so arena.o
	- rm arena.o
	mv ./libarena.so $(library_build_path)
	cp ./include/arena.h $(library_build_path)/include

json : arena.c arena.test.c
	- rm compile_commands.json
	bear -- make test
	- rm -r a.out

debug : a.out
	gdb a.out

clean : 
	- rm a.out
