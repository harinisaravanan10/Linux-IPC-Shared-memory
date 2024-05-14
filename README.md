# Linux-IPC-Shared-memory
Ex06-Linux IPC-Shared-memory

# AIM:
To Write a C program that illustrates two processes communicating using shared memory.

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - Shared Memory

### Step 3:

Execute the C Program for the desired output. 

# PROGRAM:

## Write a C program that illustrates two processes communicating using shared memory.
```
#include<unistd.h> 
#include<stdlib.h> 
#include<stdio.h> 
#include<string.h> 
#include<sys/shm.h>
#define TEXT_SZ 2048 
struct shared_use_st
{
int written_by_you;
char some_text[TEXT_SZ];
};
int main()
{
int running = 1;
void *shared_memory = (void *)0; 
struct shared_use_st *shared_stuff; 
int shmid;
srand( (unsigned int)getpid() ); 
shmid = shmget( (key_t)1234, sizeof(struct shared_use_st), 0666 |IPC_CREAT );
printf("Shared memory id is %d \n",shmid);
if (shmid == -1)
{
fprintf(stderr, "shmget failed\n");

```

## OUTPUT

![image](https://github.com/harinisaravanan10/Linux-IPC-Shared-memory/assets/149035598/99814aeb-2305-40c0-af20-8565ce1c8003)

# RESULT:
The program is executed successfully.
