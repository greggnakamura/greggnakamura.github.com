---
layout: post
title: "Kill a Stale RDP session"
excerpt: "As a remote employee, I find myself RDPing into machines on a regular basis. Everyone once in a while, I'll find that I am not able to access the remote server because there are no available sessions. "
tags: [network]
comments: true
---

As a remote employee, I find myself RDPing into machines on a regular basis. Everyone once in a while, I'll find that I am not able to access the remote server because there are no available sessions. 

In these cases, I rely on `qwinsta` and `rwinsta` to view and kick stale sessions. 

- `qwinsta` displays details about each session on the remote server
- `rwinsta` allows you to delete a session on a remote host.


To view session details:

    C:\>qwinsta /server:<nameofserver>
    SESSIONNAME       USERNAME                 ID  STATE   TYPE        DEVICE
     services                                    0  Disc
     console                                     1  Conn
                       user_session_a            2  Disc
                       user_session_b            3  Disc
     rdp-tcp                                 65536  Listen



and to remove / kill a session (user_session_a in this case):

    C:\>rwinsta 2/server:<nameofserver>



**References**:

- [Qwinsta](https://technet.microsoft.com/en-us/library/cc731503.aspx)
- [Rwinsta](https://technet.microsoft.com/en-us/library/cc754785.aspx)
