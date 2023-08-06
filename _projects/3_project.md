---
layout: page
title: Distributed File System with gRPC
description:
img: assets/img/gRPCstub.jpg
importance: 3
category: masters
---

This project involves using protocol buffers and the learning the gRPC API to write client and server code for the distributed file system. The functions were Fetch, Delete, Store, Stat and List files and the ability to recognize a timeout.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/gRPCstub.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    gRPC stub design
</div>


For the client side of the distributed system, there is the inotify watcher callback thread and the asynchronous handle callback thread. Since both threads will be performing some action on the client directory, to synchronize these two threads, both the InotifyWatch Callback function and the HandleCallBack function share a mutex. The InotifyEventCallback calls Store and Delete functions. From the HandleCallBack function, it receives the response that lists all the files on the server. These responses are asynchronous and are placed on the completion_queue. Then the Client can see if each file in the directory is present or not, or whether the modification time is the same or not. The Client then performs Fetch or Store to synchronize its local files with the server files.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/gRPCServer.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Client Architecture
</div>

On the server side, each time a client attempts to store file or delete file, the client will first call requestWriteAccess, which calls the acquirewritelock function on the server side. This function
on the serverside will check to see if the current client has the lock access to the file through a filename to clientid map. If the client is the same, then the client will have access. Otherwise, the client will not be able to get the lock. When the client who owns the lock finishes storing or deleting the file, this filename is then erased from the filename to clientid map. The server also utilizes the checksum in the fetch data and store data function. If the file on the server is the same as the file on the client, then a response of already exists will be returned.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/asyncClientGRPC.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Server Architecture
</div>

