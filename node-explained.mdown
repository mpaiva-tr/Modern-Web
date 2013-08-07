# Why is Node.js important

Node Explained [(watch video)](http://www.youtube.com/watch?v=L0pjVcIsU6A)

## Theory behind Node

### I/O Latency

I/O latency is the amount of time the information takes to be stored and processed by the main processor chip.

Cache memory is a high speed memory kept in between processor and RAM to increase the data execution speed. It is kept near to the processor.

There are different levels of cache:

- L1 cache is the fastest cache and it usually comes within the processor chip itself. The L1 cache typically ranges in size from 8KB to 64KB and uses the high-speed SRAM (static RAM) instead of the slower and cheaper DRAM (dynamic RAM) used for main memory.

- L2 cache comes between L1 and RAM(processor-L1-L2-RAM) and is bigger than the primary cache (typically 64KB to 4MB). 

The following tables give us a better way to relate how cache memory speed is compared to other conventional memory storage methods.

Intel Video explaining integrated I/O improvements in the Xeon processor: [(watch video)](http://bcove.me/hcdjit81)

| memory type |  cpu cycles | description |
|:------------|------------:|:------------|
| L1 Cache    |           3 | fastest - 8~64KB - memory located within the processor chip |
| L2 Cache    |          14 | fast - 64KB~4MB - memory located L1 and RAM |
| RAM         |         250 | fast - GB ranges - the known stacked memory boards that are added to the motherboard |
| Disk        |  41,000,000 | hard disks, solid state, usb drives |
| Network     | 240,000,000 | cloud storage |

Source: Ryan Dahl, creator of node, presented 2008-Nov-11.

|  | L2 | RAM | Disk | Network |
|:--|:--:|:--:|:--:|:--:|
| L1 | 5 | 83 | 13,666,666 | 80,000,000 faster |
| L2 | | 18 | 2,928,571 | 17,142,857 faster |
| RAM | | | 164,000 | 960,000 faster |
| Disk | | | | 6 faster |

Note: Network is slowest.

### But what makes Node fast?

- Node is fast by design;
- Never blocking on I/O means less threads;
- This means the program handles the queue for requests, not the OS.

With traditional programing languages, requests are sent to the operating system (OS), which dictates WHEN to execute each request. This is called "threading".

Node is different because it doesn't rely on getting a response from the OS to execute what needs to be done WHILE the OS is handling the previous request. This is known by the Node Event Loop.

### The Platform

The node platform is consisted of three layers:

1. Node Standard Library - APIs, modules, handles process streams and buffers;
2. Node Bindings - http, sockets, file system
3. External Resources - not written by Node:

Google's V8 
- V8 is written in C++ and translates JavaScript into machine code to talk to the hardware system [(watch video on V8)](http://www.youtube.com/watch?v=hWhMKalEicY) 
- Your computer's processor can read machine code directly. Without this step, your browser would have to translate each piece of JavaScript into machine code every time you run a script on a Web page.
- V8 runs on Windows (XP or newer), Mac OS X (10.5 or newer), and Linux systems that use IA-32, x64, or ARM processors.
V8 can run standalone, or can be embedded into any C++ application.
- V8 has better garbage collection, which means that when it finishes using memory for one task, it can better reclaim that memory for another task.
- V8 is open source and can be leveraged by any application.

What can V8 do?
SConf2012 - Vyacheslav Egorov [(watch video)](http://blip.tv/jsconf/jsconf2012-vyacheslav-egorov-6141593)

Tim Caswell: Node powered desktop apps
[watch video](http://www.youtube.com/watch?v=6XqD8h_C3ZQ)
