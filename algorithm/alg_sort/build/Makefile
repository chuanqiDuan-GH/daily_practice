#获取.cpp文件
SrcFiles=$(wildcard ../src/*.c)

#使用替换函数获取.o文件
ObjFiles=$(patsubst %.c,%.o,$(SrcFiles))

#CFLAG=-Wall -W -fsanitize=address -fno-omit-frame-pointer -O1
CFLAG=-Wall -W -fsanitize=address -fno-omit-frame-pointer -O0

#生成的可执行文件
all:alg

#目标文件依赖于.o文件
alg:$(ObjFiles)
	$(CC) $(CFLAG) -g -o ../output/$@ -I ../include/ $(SrcFiles)

#.o文件依赖于.c文件，通配使用，一条就够
%.o:%.c
	$(CC) $(CFLAG) -c -I ../include/ $<
	rm -f *.o

.PHONY:clean all

clean:
	rm -f *.o
	rm -f ../output/*
