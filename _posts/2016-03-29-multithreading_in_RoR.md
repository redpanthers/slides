---
layout: slide
title: Multithreading
description: A presentation slide for multithreading
theme: black
transition: slide
permalink: /multi-threading-in-ruby-on-rails-framework
author: Aparna V
post_thumbnail: /slides/images/multithreading.jpg
profile_image: /slides/profiles/aparnav.jpg
---

<section data-markdown>
## Multi threading in Ruby

March 29th 2016
</section>

<section>
  <h2>Aparna V</h2>
  <p>
    Ruby Developer Trainee @RedPanthers
  </p>
</section>

<section data-markdown>
### Introduction
What is threading?
- Threading often improves program response time by making heavy procedures run in the background.
- A multithreaded program has more than one thread of execution.
- Within each thread, statements are executed sequentially, but the threads themselves may be executed in parallel on a multicore CPU, for      example.
- Often on a single CPU machine, multiple threads are not actually executed in parallel, but parallelism is simulated by interleaving the execution of the threads.
</section>

<section data-markdown>
### Creating Ruby Threads
- To start a new thread, just associate a block with a call to Thread.new.
- Thread #1 is running here.
- Thread.new {
-  Thread #2 runs this code.
- }
  Thread #1 runs this code.
</section>

<section data-markdown>
- How we can use multi-threaded Ruby program.  
def func1  
i=0  
while i<=2  
puts "func1 at: #{Time.now}"  
sleep(2)  
i=i+1  
end  
end  
def func2  
j=0  
while j<=2  

</section>

<section data-markdown>
##continued
puts "func2 at: #{Time.now}"  
sleep(1)  
j=j+1  
end  
end  
puts "Started At #{Time.now}"  
t1=Thread.new{func1()}  
t2=Thread.new{func2()}  
t1.join  
t2.join  
puts "End at #{Time.now}"  
</section>

<section data-markdown>
### Threads and exceptions
- If an exception is raised in the main thread, and is not handled anywhere, the Ruby interpreter prints a message and exits. In threads other than the main thread, unhandled exceptions cause the thread to stop running.

- If a thread t exits because of an unhandled exception, and another thread s calls t.join or t.value, then the exception that occurred in t is raised in the thread s.
</section>

<section data-markdown>
- If Thread.abort_on_exception is false, the default condition, an unhandled exception simply kills the current thread and all the rest continue to run.

- If you would like any unhandled exception in any thread to cause the interpreter to exit, set the class method Thread.abort_on_exception to true.

- t = Thread.new { ... }
- t.abort_on_exception = true
</section>


<section data-markdown>
### Thread Priorities
- High-priority threads are scheduled before low-priority threads.
- You can set and query the priority of a Ruby Thread object with priority= and priority. A newly created thread starts at the same priority as the thread that created it. The main thread starts off at priority 0.
- There is no way to set the priority of a thread before it starts running. A thread can, however, raise or lower its own priority as the first action it takes.
</section>

<section data-markdown>
### Thread exclusion
- If two threads share access to the same data, and at least one of the threads modifies that data, you must take special care to ensure that no thread can ever see the data in an inconsistent state. This is called thread exclusion.
- Mutex is a class that implements a simple semaphore lock for mutually exclusive access to some shared resource. That is, only one thread may hold the lock at a given time. Other threads may choose to wait in line for the lock to become available, or may simply choose to get an immediate error indicating that the lock is not available.
</section>

<section data-markdown>
- By placing all accesses to the shared data under control of a mutex, we ensure consistency and atomic operation.
</section>

<section data-markdown>
### Muti threading vs Multiprogramming
- Ruby concurrency is when two tasks can start, run, and complete in overlapping time periods. It doesn’t necessarily mean, though, that they’ll ever both be running at the same instant (e.g., multiple threads on a single-core machine).  In Ruby, the fork() system call is used to create a “copy” of the current process. This new process is scheduled at the operating system level, so it can run concurrently with the original process, just as any other independent process can.
</section>

<section data-markdown>
### Multi processing
- using fork() to employ multiple processes:  
puts Benchmark.measure{  
  100.times do |i|  
    fork do  
      Mailer.deliver do
        from    "eki_#{i}@eqbalq.com"
        to      "jill_#{i}@example.com"
        subject "Threading and Forking (#{i})"
        body    "Some content"
      end  
    end  
  end  
  Process.waitall  
}  
</section>

<section data-markdown>
###continued
- It has a major drawback which is the amount of memory that it will consume. Forking is somewhat expensive, especially if a Copy-on-Write (CoW) is not utilized by the Ruby interpreter that you’re using.
</section>

<section data-markdown>
### Ruby Multithreading
- Multiple threads within a single process have considerably less overhead than a corresponding number of processes since they share address space and memory.
* A thread is a stream of instructions within a process. Each thread has its own instruction pointer, set of registers and stack memory. The virtual address space is process specific, or common to all threads within a process. So, data on the heap can be readily accessed by all threads, for good or ill.
</section>

<section data-markdown>
### Using multi threading  

- threads = []  
puts Benchmark.measure{  
100.times do |i|  
threads << Thread.new do  
Mailer.deliver do
from    "eki_#{i}@eqbalq.com"  
to      "jill_#{i}@example.com"  
subject "Threading and Forking (#{i})"  
body    "Some content"  
end  
end  
end  
threads.map(&:join)  }  
</section>

<section data-markdown>
- Multi-threading is a more "light weight" form of concurrency: there is less context per thread than per process. As a result thread lifetime, context switching and synchronisation costs are lower. The shared address space (noted above) means data sharing requires no extra work.
* In any multithreaded environment, context switching occurs. Context switching is the process by which a thread is stopped and its state and context are stored allowing other threads to use CPU cycles. Once the competing thread has been interrupted in a similar manner, the context and state of the original thread are loaded and the original thread has the opportunity to run if it gets priority.

</section>

<section data-markdown>
### GIL (Global Interpreter Lock).
- GIL does not make your code thread-safe. It only guarantees that two threads can’t run Ruby code at the same time. Thus it does inhibit parallelism. However, threads can still be paused and resumed at any given point, which means that they absolutely can clobber each others’ data.
- GIL makes single threaded programs faster, that multi-threaded programs are much easier to develop since the data structures are safe and finally that a lot of C extensions are not thread safe and without the GIL, these C extensions don’t behave properly.
</section>

<section data-markdown>
- An interpreter which uses GIL will always allow exactly one thread and one thread only to execute at a time, even if run on a multi-core processor.
- Ruby MRI and CPython are two of the most common examples of popular interpreters that have a GIL.
- An interpreter which uses GIL will always allow exactly one thread and one thread only to execute at a time, even if run on a multi-core processor. Ruby MRI and CPython are two of the most common examples of popular interpreters that have a GIL.
</section>

<section data-markdown>
### To make a Rails app thread-safe, you have to make sure the code is thread-safe on three different levels:

* Rails framework and its dependencies.
* Your app code.
* Any third party code you use.

</section>

<section data-markdown>
### Actors/Fibers
* Actors are a like threads which don’t share the same memory context. Communication between actors is done via exchanged messages ensuring that each actor handles its own state and therefore avoiding corrupt data (two threads can modify the same data at the same time, but an actor can’t receive two messages at the exact same time).
* A fiber is like a simplified thread which isn’t scheduled by the VM but by the programmer. Fibers are like blocks which can be paused and resumed from the outside of from within themselves. Fibers are faster and use less memory than threads.

</section>

<section data-markdown>
### continued
* Fiber allow developers to manually control the scheduling of “concurrent” code but also to have the code within the fiber to auto schedule itself.
* That’s pretty big because now you can wrap an incoming web request in its own fiber and tell it to send a response back when it’s done doing its things. In the meantime, you can move on the to next incoming request.
* Whenever a request within a fiber is done, it will automatically resume itself and be returned.

</section>

<section data-markdown>
* The only problem is that if you are doing any type of blocking IO in a fiber, the entire thread is blocked and the other fibers aren’t running. Blocking operations are operations like database/memcached queries, http requests, basically things you are probably triggering from your controllers. The only problem to fix now is to avoid blocking IOs.

</section>

<section data-markdown>
### Reference
* https://bearmetal.eu/theden/how-do-i-know-whether-my-rails-app-is-thread-safe-or-not/
* http://www.tutorialspoint.com/ruby/ruby_multithreading.htm
* http://merbist.com/2011/02/22/concurrency-in-ruby-explained/
* http://pltconfusion.com/concurrency_primitives_and_abstractions_in_ruby/
</section>

<section data-markdown>
## Thank you
</section>
