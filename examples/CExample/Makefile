CC = gcc
CFLAGS = -O2
BONMIN_INLUDE_DIR = /home/shaurya/Development/Bonmin-1.8/release/include/coin
DEBUG_LIB_DIR = /home/shaurya/Development/Bonmin-1.8/debug/lib
RELEASE_LIB_DIR = /home/shaurya/Development/Bonmin-1.8/release/lib
EXE = main

INCLUDES = -I$(BONMIN_INLUDE_DIR)
CFLAGS += $(INCLUDES)
CFLAGS += -L$(RELEASE_LIB_DIR)
CFLAGS += -Wl,-rpath=$(RELEASE_LIB_DIR)
DEBUG_LIBS = $(wildcard $(DEBUG_LIB_DIR)/*.a)
LIBS = -lbonmin -lCbc -lCbcSolver -lCgl -lClp -lClpSolver -lcoinblas -lcoinlapack -lcoinmumps -lCoinUtils -lOsiCbc -lOsiClp -lOsi
LIBS += -lipopt -llapack -ldl -lcoinhsl -lblas -lgfortran -lm -lquadmath -lstdc++ -lz

all : MyBonmin.o main

MyBonmin.o : MyBonmin.c
	$(CC) -c $(CFLAGS) -o MyBonmin.o MyBonmin.c

# main : main.c MyBonmin.o
# 	$(CC) $(CFLAGS) -o main main.c MyBonmin.o $(DEBUG_LIBS) $(LIBS)


main : main.c MyBonmin.o
	$(CC) $(CFLAGS) -o main main.c MyBonmin.o $(LIBS)

clean :
	rm -f $(EXE) MyBonmin.o
