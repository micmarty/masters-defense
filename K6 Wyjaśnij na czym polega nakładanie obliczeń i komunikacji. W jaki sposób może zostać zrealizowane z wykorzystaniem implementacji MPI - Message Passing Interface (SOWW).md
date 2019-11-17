# K6 Wyjaśnij na czym polega nakładanie obliczeń i komunikacji. W jaki sposób może zostać zrealizowane z wykorzystaniem implementacji MPI - Message Passing Interface
Źródło: http://fox.eti.pg.gda.pl/~pczarnul/PCzarnul-papers/2007/pczarnulkaskbook2007.pdf

MPI wyróżnia funkcję komunikacji nieblokującej asynchronicznej, zarówno po stronie nadawcy i odbiorcy: `MPI_Isend, MPI_Ibsend, MPI_Issend, MPI_Irsend, oraz MPI_Irecv`. 

Funkcje te rozpoczynają odpowiednie operacje wysyłania i odbioru zwracając uchwyt (`MPI_Request`), który służy do zakończenia wyżej wymienionych operacji przez wywołanie funkcji rodziny `MPI_Wait*`. Po wywołaniu funkcji `MPI_I*` proces może wykonać inne operacje pozwalające potencjalnie na wykonanie obliczeo i komunikacji równolegle


zrodlo: http://parallelcomp.uw.hu/ch06lev1sec5.html
> Note that the MPI_Irecv function does not take a status argument similar to the blocking receive function, but the status information associated with the receive operation is returned by the MPI_Test and MPI_Wait functions. MPI_Test tests whether or not the non-blocking send or receive operation identified by its request has finished.

```
int MPI_Test(MPI_Request *request, int *flag, MPI_Status *status) 
int MPI_Wait(MPI_Request *request, MPI_Status *status) 
```



> Avoiding Deadlocks By using non-blocking communication operations we can remove most of the deadlocks associated with their blocking counterparts. 

> Note that in order to overlap communication with computation we have to use two auxiliary arrays - one for A and one for B. This is to ensure that incoming messages never overwrite the blocks of A and B that are used in the computation, which proceeds concurrently with the data transfer. Thus, increased performance (by overlapping communication with computation) comes at the expense of increased memory requirements.
