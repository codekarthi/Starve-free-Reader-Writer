# Starve-free-Reader-Writer

## The Problem is:
### 1. Reader: Can only read the data.
###    Writer: Can read and update the data
### 2. Any number of readers can read the data parallely but writer,reader or writer,writer should not be done parallely.
### 3. No starvation should be present.
## The following is the explanation of the psuedocode for starve-free reader-writer problem
###  1. There are three semaphores 
>            ### a) mutex : mutual exclusion for updating readcount variable (binary semaphore) 
             ### b) wrt   : mutual exclusion semaphore for writers
             ### c) access: To maintain the order in which the proccesses come (TO MAINTAIN STARVE-FREE ).
###     All are initialised to one.
###  2. readcount variable to count number of readers.(initialised to zero).
###  3. Lets say R-Reader process and W-Writer process.
###                    The proccesses arE as follows RRRWRRR
###                    In the  Reader process:
###                                     mutex semaphore will do its job to correctly count the number of varialbles.
###                                     wrt will become zero if readcount=1 and the write proccess will wait.
###                                     After all the reader process will read then readcount =0 and wrt will become one .
###                    In the Writer process:
###                                     After all readers before writer process is initialised are completed then writer wii write and update the data.
###                    Use of access semaphore:
###                                     In the above example when the W has come then access becomes zero and until the write process is completed all readers after                                            writer will wait.By this we can remove the starvation. My logic is FCFS (First Come First Serve).
                    
                                     
                                   
                    


