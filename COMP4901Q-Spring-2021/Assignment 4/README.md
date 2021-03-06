# COMP4901Q: Assignment 4
## Compiling
This is the basic command to compile and run the program. Ensure that the hosts in the hostfile are known hosts.

```
nvcc -I . -I utils -I ../utils -I /usr/local/software/openmpi/include/ -L /usr/local/software/openmpi/lib/ -l mpi -std=c++11 -Wno-deprecated-gpu-targets -O2 main.cu -D PRINT_OUTPUT
mpiexec --hostfile hostfile -x "LD_LIBRARY_PATH=/usr/local/software/openmpi/lib:$LD_LIBRARY_PATH" -n 4 ./a.out
```

Configure the program by specifying the following compilation flags:
* `-D RUNS=100`. Specify the number of runs. By default, this value is 10.
* `-D PROBLEM=1`. Specify which problems to run. You can run both problems by using `-D PROBLEM=12`. By default, both problems 1 and 2 are run.
* `-D PRINT_OUTPUT`. Controls whether output is printed. However, even if activated, output will only be printed if the input is small to avoid cluttering the terminal.
* `-D RANDOM_LO=1.0`. Specify the lower bound of numbers to be generated. By default, this is 1.0.
* `-D RANDOM_HI=10.0`. Specify the upper bound of numbers to be generated. By default, this is 10.0.

<!-- ## Running -->

<!-- TODO -->


<!--
Useful SSH Commands:
```
ssh user@host
scp -r . user@host:/destination/path
ssh-keygen -q -t rsa -N "" -f ~/.ssh/id_rsa
ssh-copy-id user@host
ssh -o StrictHostKeyChecking=no host
```
-->