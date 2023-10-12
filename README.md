# OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE

## AIM:
Write C programs to illustrate IPC using pipes mechanisms.
## ALGORITHM:
Create a child process usingfork()
<br>
Create a simple pipe with C, we make use of the pipe() systemcall.
<br>
Create two file descriptor fd[0] is set up for reading, fd[1] isset up forwriting
<br>
Close the read end of parent process using close() and perform writeoperation
<br>
Close the write end of child process and performreading
<br>
Display thetext.
<br>

## PROGRAM:
```
#include <stdio.h>
int main()
{
int fd[2],child; char a[10];
printf("\n Enter the string:");
scanf("%s",a);
pipe(fd);
child=fork();
if(!child)
{
close(fd[0]);
write(fd[1],a,5); wait(0);
}
else
{
close(fd[1]);
read(fd[0],a,5); printf("The string received from pipe is: %s",a);
}
return 0;
}
```
## OUTPUT:

![image](https://github.com/kavinesh8476/OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE/assets/118466561/3324bc27-898d-4239-9df2-a8eda27f8bc1)


## RESULT:
Thus, IPC using pipes mechanisms is illustrated using c program successfully.
