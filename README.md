# readerwriterlocks
Implementation of reader writer locks in java
/*This file implements read-write locks. readacquire() and readrelease() are methods 
 * for acquiring and release locks while reading data. Writeacuqire() and writerelease are methods for
 * writing data. Readacquire can acquire lock for read if there are no writing threads in
 * the critical section (CS), though it can acquire a lock if there are multiple reader threads in CS.
 * Writeacquire() method can acquire a lock only when there in no reader thread or writer thread in the CS.
 * Readerrelease() method release the read lock and decrement the reader thread counter and then wake:
 * 1. One writer thread first (if there is any)
 * 2. Then wakes all the reader threads (if there is any)
 * Writerelease release the write lock and decrement the writer count which can be either 0 or 1 only. 
 * It then wake:
 * 1. All the reader threads waiting  to acquire lock(if any exist)
 * 2. wake one writer thread  waiting  to acquire lock (if there is any)
 * 
 * */
