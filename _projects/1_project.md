---
layout: page
title: Multithreaded GetFile Server/Client
description:
img: assets/img/mtfs.jpg
importance: 1
category: masters
---

In this project, I designed and implement a multi-threaded server that serves static files based on the GetFile protocol, which is a simple HTTP-like protocol. Alongside the server, I also created a multi-threaded client that acts as a load generator for the server. Both the server and client were written in C. While I can not show the code, I have the design for my implementation shown below.


For both the client and the server, I followed a boss-worker thread pattern. 

On the server side, the boss thread listens to the socket and accepts new connection requests. The new connections are fully handled by worker threads.

On the client side, a pool of worker threads are initialized. Once the worker threads have been started, the boss enqueues the requests to them. They should continue to run. Once the boss confirms all requests have been completed, it terminates the worker threads and exit.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/mtfs.jpg" title="multithreaded file server" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
     design for the multithreaded file server
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/mtfc.jpg" title="multithreaded file server" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    design for the multithreaded getFile client
</div>