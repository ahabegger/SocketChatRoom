# CSE 278 Project: Chatting Room

## Overview
This is a simple chat room project that allows two users to communicate with each other. The functionalities include user authentication, sending messages, and file sharing. This project is created by Alex Habegger and Nathan Abdoo for the CSE 278B Systems I class under the supervision of Professor Xianglong Feng.

## Features
- User authentication (login check)
- Free chatting (send and receive messages instantly)
  - Send messages to all users (type message as normal)
  - Send private messages to one user (`/p user message`)
- File sharing
  - Send files to all users (`/f file.txt`)
  - Send files privately to one user (`/u user file.txt`)
- Exit the client without using Ctrl + C (`/e` or `/exit`)

## Files and Functions
### SocketServer.cpp
- `thread_server(int socket)`: Checks if the received message is a loginAttempt.
- `loginAttempt(char* loginInfo, int socket)`: Performs an SQL query on the database to check login credentials.
- `thread_Send(int socket)`: Sends messages to clients.
- `thread_Receive(int socket)`: Receives messages from clients and checks if the received message is a loginAttempt.
- `int main(int argc, char const *argv[])`: Creates threads for handling client connections.

### SocketClient.cpp
- `thread_Send(int socket)`: Handles sending messages and files, as well as exiting the client.
- `thread_Receive(int socket)`: Handles receiving messages and files from other users.
- `checkLogin(string username, string password, int socket)`: Sends loginAttempt to the server and sets the user title.
- `main(int argc, char const *argv[])`: Handles the login loop and creates send and receive threads.

### Makefile
- Compiles both SocketServer.cpp and SocketClient.cpp.

## Contact Information
- Team Members: Alex Habegger (habeggaj) and Nathan Abdoo (abdoojm)
- Contact Emails: habeggaj@miamioh.edu, abdoojm@miamioh.edu
