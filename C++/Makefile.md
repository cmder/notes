教程：

http://c.biancheng.net/view/7097.html

makefile介绍：

https://zhuanlan.zhihu.com/p/100964932

完整过程

```makefile
CC=gcc
CFLAGS=-g -Wall
LIBS=-lm
OBJ=main.o
$(OBJ):main.c
    $(CC) $(CFLAGS) -c main.c -o $(OBJ)
TARGET=main
$(TARGET):main.o
    $(CC) $(CFLAGS) -o $(TARGET) $(OBJ) $(LIBS)
.PHONY:clean
clean:
    rm $(OBJ) $(TARGET)
```

可以看到，makefile文件中有三个目标，分别是main.o，main和clean，其中clean是一个伪目标。

