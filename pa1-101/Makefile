#------------------------------------------------------------------------------
# Makefile for CSE 101 Programming Assignment 1
#
# make                   makes Lex
# make ListClient        makes ListClient
# make clean             removes all binaries
# make checkClient       checks ListClient for memory errors
# make checkLex          checks Lex for memory errors
#------------------------------------------------------------------------------

Lex : Lex.o List.o
	gcc -std=c11 -Wall -o Lex Lex.o List.o

Lex.o : Lex.c List.h
	gcc -std=c11 -Wall -c -g Lex.c

ListClient: ListClient.o List.o
	gcc -std=c11 -Wall -o ListClient ListClient.o List.o

ListClient.o : ListClient.c List.h
	gcc -std=c11 -Wall -c ListClient.c

List.o : List.c List.h
	gcc -std=c11 -Wall -c -g List.c

clean :
	rm -f Lex ListClient Lex.o ListClient.o List.o

checkClient : 
	valgrind --leak-check=full ListClient

checkLex : 
	valgrind --leak-check=full --track-origins=yes --show-leak-kinds=all -v Lex in out
