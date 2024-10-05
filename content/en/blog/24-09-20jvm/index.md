---
title: "[java] JVM Garbage Collector"
date: 2024-09-20
image:
  focal_point: 'top'
---
<a href="https://bong0920.tistory.com/1" class="btn btn-primary">Read the blog</a>


<!--more-->

What is a Garbage Collector?
Garbage Collector (GC) automatically manages dynamic memory allocation requests from applications.

Garbage Collector does the following

Allocates and returns memory to the operating system.
Delivers that memory to applications as they request it.
Determines what portion of that memory is still in use by the application.
Reclaims unused memory so that it can be reused by the application.
The Java HotSpot garbage collector uses a variety of techniques to increase the efficiency of these tasks.

Generationally manages the heap region to focus on areas that are likely to become garbage in order to use resources efficiently.
It uses multiple threads to parallelize tasks or perform some long-running tasks in the background at the same time as the application.
