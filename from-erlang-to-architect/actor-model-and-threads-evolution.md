```
If erlang/OTP and actor model was around for such a long time, why popular solutions like Spring, python and ruby WSGI, PHP used system threads and thread pools for such a long time? Was nodejs really a breackthrought in this sense? On OS level there were other different parrallel and async solutions developing too, IPC, etc...  what models did they use?
```

You've touched on a fascinating aspect of computing history! The persistence of thread-based models despite the existence of more elegant solutions like the actor model reveals a complex interplay of technical, practical, and cultural factors:

### Why Thread Pools Dominated

1. **Familiarity and Conceptual Simplicity**
   - Threads map directly to how most developers think about concurrent execution
   - The mental model aligns with sequential programming that most developers learned first

2. **Ecosystem Maturity**
   - Thread-based libraries, tooling, and debugging were well-established
   - Massive investment in thread-based programming patterns and frameworks

3. **Platform Integration**
   - OS kernels and C libraries were optimized for thread-based concurrency
   - Threading primitives were standardized (POSIX threads) across platforms

4. **Pragmatic Concerns**
   - Many applications didn't need the extreme concurrency Erlang offered
   - For typical web applications, thread pools with 10-100 threads were often sufficient

### Node.js as a Breakthrough

Node.js was indeed transformative, but not because it introduced new concepts (event loops existed before). Its breakthrough was:

1. **Accessibility**: It brought single-threaded event-driven programming to mainstream web developers
2. **Ecosystem**: It created a unified paradigm and package ecosystem around async patterns
3. **Timing**: It arrived when web applications were hitting concurrency walls with traditional approaches
4. **Programming Model**: JavaScript's closure model made callbacks and later promises natural

### OS-Level Models

Operating systems historically used several models for parallelism:

1. **Process-based**: Full isolation, heavyweight (Unix philosophy)
2. **Thread-based**: Shared memory, lightweight processes (Windows NT, modern Unix)
3. **Event-driven**: Select/poll/epoll models for I/O multiplexing
4. **Message-passing**: Microkernel designs (Mach) used IPC as fundamental building blocks
5. **Hybrid approaches**: Most modern OSes combine these models

### The Technology Adoption Curve

The actor model and Erlang, despite technical superiority for certain problems, faced adoption barriers:

- **Paradigm shift**: Required fundamentally different thinking about program structure
- **Functional roots**: Many developers were more comfortable with imperative programming
- **Perceived niche**: Often viewed as suitable only for telecom or specialized systems
- **Corporate backing**: Lacked the marketing and ecosystem investment of Java/Spring

The rise of cloud computing, microservices, and need for extreme scalability has finally pushed more developers toward these distributed programming models, but it took decades for the industry to "rediscover" what Erlang had quietly provided since the 1980s.

This pattern of rediscovery is common in computer science - elegant solutions often exist for years before becoming mainstream when the broader ecosystem and developer mindset catch up to them.