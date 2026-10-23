# MUHAMMAD IMAMUL KHAIR BIN AMERAN
NETWORK PROGRAMMING WITH C

Introduction

Every time a phone loads a web page, sends a chat message or syncs a file, two programs are talking to each other across a network. Network programming is the skill of writing those programs. In this article I explain the basics of network programming in C and build a small working example: a TCP server that receives a message from a client, records it with a timestamp, and sends it back in capital letters.

C is a good language for learning this topic for three reasons. First, the socket interface that almost every other language uses (Python, Java, Node.js and so on) was originally designed for C on Unix, so learning it in C shows what is really happening underneath. Second, C gives direct control over the system calls, so nothing is hidden. Third, a lot of real network software, including web servers and network tools, is still written in C.

By the end of this article you will understand what a socket is, how a TCP connection is set up, and how to compile and run a client and server of your own. A video demonstration is linked at the top of this page.

Background

What is a socket?

A socket is an endpoint for communication provided by the operating system. A program asks the operating system for a socket, and the operating system returns a file descriptor, which is just an integer. The program then reads from and writes to that descriptor in much the same way it would use a file, except the data travels over the network.

Each side of a conversation is identified by an IP address (which machine) and a port number (which program on that machine). For example, 127.0.0.1:8080 means "port 8080 on this same computer", where 127.0.0.1 is the loopback address used for testing.
