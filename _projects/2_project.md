---
layout: page
title: Shared-Memory IPC
description: 
img: assets/img/cache.jpg
importance: 2
category: masters
---
This projects creates a proxy that takes in GETFILE requests and translates them into http requests into a different server.  A cache process is also implemented that runs on the same machine as the proxy and communicates with it via shared memory. I learned and used the POSIX API, message queue and semaphores to implement the shared-memory component. 

When a request comes in, the GETFILE Proxy queries the cache to see if the file is available in local memory already before relaying requests to the http server.

In the interprocess communication, the proxy creates and destroys the shared memory. The cache then sets up the shared memory by which the proxy communicates its request along with the shared memory name to obtain the file.

The design choices I made were using POSIX shared memory API, POSIX message queue API and semaphores. I chose the POSIX shared memory API as it was easier to use and found many practical examples where I could learn from. I used the message queue to pass information along from the cache handler to the cache server because I could pass struct through the message queue, whereas I would have to format every string if I used the socket method. Lastly I used the semaphore read and semaphore write when the information was being passed along the shared memory. I chose semaphores because they are more flexible to
use than a mutex.


<div class="row">
<div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/part2.jpg" title="architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/cache.jpg" title="cache proxy design" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Design for shared-memory IPC getfile proxy
</div>