# CS525-Advanced-Database-Organisation
Assignments implemented in this course
# Storage Manager: 
Implemented a storage manager that allows read/writing of blocks to/from a file on disk
# Buffer Manager:
Implemented a buffer manager that manages a buffer of blocks in memory including reading/flushing to disk and block replacement (flushing blocks to disk to make space for reading new blocks from disk). Implemented LRU and FIFO page replacement strategy. The below additional points were also implemented:

Multithreading: 

  a. Implemented the buffer manager program such that the program supports multithreading. 
  
  b. In order to implement Multithreading we used pthread.h which is a threading header used in linux systems. 
  
  c. Used the BM_LOCK and BM_UNLOCK functions to lock and unlock the buffer in operation
  
  d. Once the buffer is locked by the user pthread.h will help to manage the multithreads 

Additional replacement strategy: 

  a. LRU-K is implemented as a extra replacement strategy.
  
  b. For LRU-K we have implemented LRU-3 wherein the 3rd least recently used page is replaced with the new page when the buffer is full. 
  
  c. The code uses LRU strategy and finds the 3rd least recently used page from the buffer 
  
  d. Once the page is recognized, in case the page has fixcount is greater than zero the next least recently used page is replaced with the new page in the buffer.

# Record Manager: 
Implement a simple record manager that allows navigation through records, and inserting and deleting records. The below additional points were also implemented:

Primary key constraints:  
  
  a. Implemented the record manager with primary key constraints.
  
  b. Created a key with one of the columns for e.g. "a"
  
  c. While trying to insert records in the table with same values in "a" the value in the column will be incremented such that duplicate records will not be inserted in the table. 
  
  d. This is implemented in all the test cases more specifically in "testInsertmanyRecords"

Interactive interface:
  
  a. An interactive interface is created which helps to create a table based on the column names inputed by the user. 
  
  b. The interface asks for column name and its corresponding datatype. The correct values of the datatype are: "INT, STRING, FLOAT & BOOL"
  
  c. In case the datatype is string, the length of the string is asked from the user
  
  d. Based on the inputs from the user, a schema is created. 
  
  e. Once the schema is created the records are inserted in the table and displayed to the user as required. 

Handled memory issues:

Handled memory issues in the test case by freeing the record and the rids created in the test case using free(record) and free(rid)

# B+-Tree Index: 

Implemented a disk-based B+-tree index structure
