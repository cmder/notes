http://wiki.dreamrunner.org/public_html/Linux/addr2line-usage.html

.c文件（gcc -g hello.c）——》.out（objdump命令）——》反汇编文件（可查看地址）

addr2line .out 地址 ——》文件名：行号

反汇编后的文件：

```
Disassembly of section .text:

0000000000400440 <_start>:
  400440:       31 ed                   xor    %ebp,%ebp
  400442:       49 89 d1                mov    %rdx,%r9
  400445:       5e                      pop    %rsi
  400446:       48 89 e2                mov    %rsp,%rdx
  400449:       48 83 e4 f0             and    $0xfffffffffffffff0,%rsp
  40044d:       50                      push   %rax
  40044e:       54                      push   %rsp
  40044f:       49 c7 c0 c0 05 40 00    mov    $0x4005c0,%r8
  400456:       48 c7 c1 50 05 40 00    mov    $0x400550,%rcx
  40045d:       48 c7 c7 2d 05 40 00    mov    $0x40052d,%rdi
  400464:       e8 b7 ff ff ff          callq  400420 <__libc_start_main@plt>
  400469:       f4                      hlt    
  40046a:       66 0f 1f 44 00 00       nopw   0x0(%rax,%rax,1)
...
000000000040052d <main>:
#include <stdio.h>
int main()
{
  40052d:       55                      push   %rbp
  40052e:       48 89 e5                mov    %rsp,%rbp
    printf("hello\n");
  400531:       bf d4 05 40 00          mov    $0x4005d4,%edi
  400536:       e8 d5 fe ff ff          callq  400410 <puts@plt>
    return 0;
  40053b:       b8 00 00 00 00          mov    $0x0,%eax
}
  400540:       5d                      pop    %rbp
  400541:       c3                      retq   
  400542:       66 2e 0f 1f 84 00 00    nopw   %cs:0x0(%rax,%rax,1)
  400549:       00 00 00 
  40054c:       0f 1f 40 00             nopl   0x0(%rax)
...
```

使用addr2line命令：

```
$ addr2line -e a.out 0x400442 #offset in the `__start` function
??:?
$ addr2line -e a.out 0x40052d #offset in the `main` function
hello.c:3
$ addr2line -e a.out 0x40054c -f #The last instruction of the `main` function
main
??:?
```

