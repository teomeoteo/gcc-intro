# Learning Process

## First Lessons
Used gcc -Wall [program.c] -o [target] to create executables immediatelly\
Used gcc -Wall -c [program.c] to create object files first and then gcc [object.o] -o [target]\
Used makefile to compile

## Search paths, dynamic libraries, linker input

### gcc compilation process

1. preprocessing(expand macros)
2. compilation(from source to assembly)
3. assembly(from assembly to machine code)
4. linking(create final exe)
---
1. Expanding macros like #include statements actually copies the .h file's code into the .i file.
Then in the linking stage those function declarations for example are connected to libraries that
include the implementation. -note we're using "cpp" command like so: "cpp filename.c > filename.i"

2. The assembly code generated from the .i file [gcc -Wall -S(this instructs the compiler to stop
once assembly is created and not to go on to create objects)filename.i] does include calls to functions such as for example "call printf"
-note that we are using "gcc" command since this is the compilation process from the .i file to the assembly .s file

3. Converting aseembly into machine code and generating an object file. Addresses of external func-
tions are left undefined, to be filled in the linking process. "as filename.s -o filename.o"
-note that we're using "as" command to move from the .s file to an .o file

4. And finally linking of the .o file to libraries in order to get the functionality needed for an executable.
This stage takes in machine code from the .o file and combines it with libraries. In order to properly use "ld"
command for linking we'd need to specify a lot ofdependancies. Those default dependancies can be skipped if we use
"gcc" again "gcc filename.o".

