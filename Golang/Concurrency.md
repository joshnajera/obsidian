Running in parallel with golang is easy. 

```go
go functionName
```
This automatically launches new green thread, which runs asynchronously.

Since the thread is asynchronous, the order/time of execution cannot be guaranteed. It may be necessary to await threads to be finished.
