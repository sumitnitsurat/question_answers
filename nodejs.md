**1. If nodejs is single threaded then how is handles concurrency?**

```
    Node provides a single thread to the programmers so that code can be written easily and without bottleneck. Node internally uses multiple POSIX threads for the various I/O operations such as File, DNS, Network Calls etc.

    When Node gets I/O request it creates or uses a thread to perform the I/O operation and once the operation is done, it pushes the result to the event queue. On each such event, event loop runs and check the queue and if the execution stack of Node is empty then it adds the queue result to the execution stack.

    This is how Node manages concurrency.

```