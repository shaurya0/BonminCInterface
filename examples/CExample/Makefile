CC = gcc
CFLAGS = -O2
BONMIN_INLUDE_DIR = /home/shaurya/Development/Bonmin-1.8/release/include/coin
INCLUDES = -I$(BONMIN_INLUDE_DIR)
EXE = main
CFLAGS += $(INCLUDES)
DEBUG_LIB_DIR = /home/shaurya/Development/Bonmin-1.8/debug/lib
RELEASE_LIB_DIR = /home/shaurya/Development/Bonmin-1.8/release/lib
DEBUG_LIBS = $(wildcard $(DEBUG_LIB_DIR)/*.a)

all : MyBonmin.o main

MyBonmin.o : MyBonmin.c
	$(CC) -c $(CFLAGS) -o MyBonmin.o MyBonmin.c

main : main.c MyBonmin.o
	$(CC) $(CFLAGS) -o main main.c MyBonmin.o $(DEBUG_LIBS) -lipopt -llapack -ldl -lcoinhsl -lblas -lgfortran -lm -lquadmath -lstdc++ -lz

clean :
	rm -f $(EXE) MyBonmin.o
