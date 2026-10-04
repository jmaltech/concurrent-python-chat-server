# Concurrent Python Chat Server

A real-time client-server chat application built with Python sockets and multithreading. The project allows multiple clients to connect to a central server, choose a nickname, and exchange messages in real time.

## Features

- Multiple clients can connect simultaneously
- Real-time message broadcasting
- Nickname-based chat messages
- Join and leave notifications
- Concurrent client handling with Python threads
- Graceful client disconnect handling

## Technologies

- Python 3
- `socket`
- `threading`
- TCP/IP networking

## How It Works

The server listens on `127.0.0.1:5555` and accepts incoming TCP connections. Each connected client is handled on its own thread so multiple users can communicate at the same time.

When a client connects, the server requests a nickname and stores the client's socket and nickname. Messages received from one client are broadcast to all connected clients. If a client disconnects, the server removes that connection and notifies the remaining users.

The client uses two threads:

1. A receive thread that listens for messages from the server.
2. A write thread that sends the user's messages to the server.

## Project Structure

```text
concurrent-python-chat-server/
├── README.md
├── server.py
└── client.py
```

## Running the Project

### 1. Clone the repository

```bash
git clone https://github.com/jmaltech/concurrent-python-chat-server.git
cd concurrent-python-chat-server
```

### 2. Start the server

```bash
python3 server.py
```

You should see:

```text
Server is running...
```

### 3. Start a client

Open a second terminal and run:

```bash
python3 client.py
```

Enter a nickname when prompted.

### 4. Test multiple clients

Open additional terminal windows and run `python3 client.py` in each one. Each client can send and receive messages in real time.

## What I Learned

This project gave me hands-on experience with TCP socket programming, multithreading, client-server architecture, real-time communication, and handling disconnected clients.

## Future Improvements

- Add a graphical user interface
- Support private messages
- Add chat rooms
- Add timestamps to messages
- Improve error handling and server shutdown behavior

## Author

Jamaal Abdi
