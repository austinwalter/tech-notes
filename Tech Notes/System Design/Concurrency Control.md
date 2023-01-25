# Concurrency Control

### Timestamp ordering
- Assign unique timestamp to a transaction when it begins
- Each object has a read and write timestamp associated with it
	- which committed transaction last read the object
	- which committed transaction last wrote the object
- Good ordering:
	- object’s read and write timestamps will be older than current transaction if it wants to write an object
	- object’s write timestamps will be older than current transaction if it wants to read an object
- Abort and restart transaction for improper ordering

## Reference
https://people.cs.rutgers.edu/~pxk/rutgers/notes/content/concurrency-notes.pdf