# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

Developed by: ADITAAYAN M

Register number: 212223040006


## C Program to print process ID and parent Process ID using Linux API system calls

```
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main(void)
{	//variable to store calling function's process id
	pid_t process_id;
	//variable to store parent function's process id
	pid_t p_process_id;
	//getpid() - will return process id of calling function
	process_id = getpid();
	//getppid() - will return process id of parent function
	p_process_id = getppid();
	//printing the process ids

//printing the process ids
	printf("The process id: %d\n",process_id);
	printf("The process id of parent function: %d\n",p_process_id);
	return 0; }
```

## OUTPUT

![365893605-7c831f9f-865a-4518-85b7-f97eccf7b5dc](https://github.com/user-attachments/assets/44a88ffc-505f-47b7-a5d1-76fe9a9abfa9)



## C Program to create new process using Linux API system calls fork() and exit()

```
#include <stdio.h>
#include<stdlib.h>
int main()
{ int pid; 
pid=fork(); 
if(pid == 0) 
{ printf("Iam child my pid is %d\n",getpid()); 
printf("My parent pid is:%d\n",getppid()); 
exit(0); } 
else{ 
printf("I am parent, my pid is %d\n",getpid()); 
sleep(100); 
exit(0);} 
}
```

## OUTPUT



![365893738-78cca457-afd3-47ae-8af2-fb79c5f42379](https://github.com/user-attachments/assets/65c95b63-b861-4778-b2e9-ed7b27bd03f6)

## C Program to execute Linux system commands using Linux API system calls exec() family


```
#include <unistd.h>
#include <stdio.h>
#include <stdlib.h>
int main()
{
	printf("Running ps with execlp\n");
	execlp("ps", "ps", "ax", NULL);
	printf("Done.\n");
	exit(0);
}
```


## OUTPUT


![365893899-4ce61599-1bc9-4710-885f-b865f6eabf03](https://github.com/user-attachments/assets/f90333f4-bbe8-4ec2-b9c0-a99d85c37a00)



# RESULT:
The programs are executed successfully.
