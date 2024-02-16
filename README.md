# cDSA
This is a collection of data structures, algorithms, and other objects to build stuff in C.
<br>
<br>

## Motivation
If you have tried to build anything in C you know the standard library provides the beautiful bare-bones tools needed for smaller tasks, but lacks the richness of an ecosystem like JavaScript and Python with readily-available access to dictionaries, array lists, and other stuff. I built this library to provide the same access to fundamental data structures and algorithms available in other languages.
<br>
<br>

## Installing
To build any given data structure and get the .so file go into that directory and run:
```
make library
```
This will create a .so and move both the .so and copy of the header file to the lib/ directory.
<br>
<br>
<br>
There are tests written for each and if you would like to run the tests go into the directory and run:
```
make test
./a.out
```

