---
title: Netty 101
date: 2024-07-14 14:04:54
tags: Netty, Random keynote
categories: 
   - Netty

---

# TODO:
- [Alr watched the video](https://www.bilibili.com/video/BV1oT411J7Zh/?spm_id_from=333.788.recommend_more_video.11&vd_source=0954589fea8abfa18b6bebeb41768a7c), do some note


Highlight

1. Netty 3 vs Netty 4: 
  - Netty 3 got too much garbage -> trigger GC more often
  - dont have a good memory pool (e.g pooling for ByteBuf in Netty 4)
    - high performance buffer pool based on jemalloc
  - not optimized for Linux (point 4)
  - threading model is not easy to reason about

2. Pipeline: Chain of Responsibility Pattern 責任鏈模式
  - channel is an abstract of socket
  - each channel has a channel pipeline 
  - pipeline contains one or more `channel inboud handler` and `channel outbound handler`, which is a Intercepting Filter Pattern (scalable, flexable), e.g diff network protocol, encoder/decoder

3. Object pool: reduce obj create and GC
4. high performance IO - Epoll
  - JNI, write some C code use epoll 

5. ByteBuf: ByteBuffer from Java is not good enough
  - Netty wont follow the max memory limit you set in command line 
  - Netty has a memory leak detector
  - Pooling ByteBuf (`PooledByteBufAllocator` based on jemalloc)
  - Jemalloc

6. Thread Model: 
  - good design reduce thread context switching
  - channel bind to a IO-Thread and never change, all ops are done in the same thread
  - IO-Thread fire event from `channel inboud handler` and `channel outbound handler`, and we dont need to care about sync problem anymore (as everything in the same thread)
    - except a channel handler shared by more than 1 channel
   - decouple `write()` and `flush()` -> `writev()` in JNI/C -> syscall 
   - challenge: the timing to call `flush()`, as msg is stack in Java memory, can be huge