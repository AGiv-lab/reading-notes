# Reading 12: Socket.io

## WebSockets

**Resource:** [WebSocket — Wikipedia](https://en.wikipedia.org/wiki/WebSocket)

### 1. What is a WebSocket?

A WebSocket is a communication protocol that allows two-way, real-time communication between a client and server over a persistent connection.

### 2. Describe the WebSocket request/response handshake and what happens once the connection is established.

1. The client sends an HTTP request asking to upgrade the connection to WebSocket.
2. The server accepts with a `101 Switching Protocols` response.
3. The connection stays open, allowing both sides to send messages independently.

### 3. WebSockets provide a standardized way for the server to send content to a client without first receiving a ___ from that client.

**Request.**

The server can send updates without waiting for another client request.

---

## Socket.io Tutorial

**Resource:** [Socket.io Tutorial — TutorialsPoint](https://www.tutorialspoint.com/socket.io/)

### 1. What does the event handler `io.on()` do?

`io.on()` registers an event listener on the Socket.IO server. It is commonly used to detect new client connections.

```javascript
io.on('connection', (socket) => {
  console.log('Client connected');
});
```

### 2. Describe some possible proof of life or proof that the code works as expected.

- The server displays a connection message.
- A client successfully connects.
- A message sent by one client appears in another client's browser.
- The server logs incoming events.

### 3. What does `socket.emit()` do?

`socket.emit()` sends a named event with optional data to the connected recipient.

```javascript
socket.emit('message', 'Hello World!');
```

---

## Socket.io vs. WebSockets

**Resource:** [WebSocket vs. Socket.io — EDUCBA](https://www.educba.com/websocket-vs-socket-io/)

### 1. What is the difference between WebSocket and Socket.IO?

- **WebSocket:** A communication protocol for real-time, two-way messaging.
- **Socket.IO:** A JavaScript library that provides event-based communication, automatic reconnection, rooms, namespaces, and transport fallbacks.

WebSocket is the underlying standard, while Socket.IO provides additional features. Socket.IO is not simply a standard WebSocket implementation.

### 2. When would you use Socket.IO?

When building applications that benefit from built-in event handling and connection management.

Examples:
- Chat applications
- Multiplayer games
- Live notifications
- Delivery tracking

### 3. When would you use WebSockets?

When an application needs direct, (persistent connection)/real-time communication using the standard WebSocket protocol without Socket.IO's additional features.

---

## OSI Model Explained

**Video:** [OSI Model Explained](https://www.youtube.com/watch?v=vv4y_uOneC0)

### What are a couple of key takeaways?

- The OSI model divides network communication into **seven layers**.
- Each layer has a specific responsibility, from physical data transmission to application communication.
- The model helps developers understand and troubleshoot networking problems.

---

## TCP Handshakes Explained

**Video:** [TCP Handshakes Explained](https://www.youtube.com/watch?v=xMtP5ZB3wSk)

### Explain the gist to a non-technical friend.

A TCP handshake is like starting a phone conversation.

1. **SYN:** One person asks, "Can we talk?"
2. **SYN-ACK:** The other responds, "Yes, I hear you."
3. **ACK:** The first replies, "Great, let's begin."

This three-step process establishes a connection before data is exchanged.

---

## Things I Want to Know More About

1. How does Socket.IO reconnect when a client loses internet access?
2. How do rooms and namespaces organize communication between users?
3. When is a REST API more appropriate than WebSockets?
4. How can Socket.IO be used in a real-time delivery tracking application?

## Key Takeaway

WebSockets provide persistent, two-way communication between clients and servers. Socket.IO builds on real-time communication concepts by adding event handling, reconnection, and tools for organizing connected clients.
## Resources

- [Socket.io Documentation](https://socket.io/docs/v4/)
- [Socket.io Emit Cheatsheet](https://socket.io/docs/v4/emit-cheatsheet/)
- [Node.js Events](https://nodejs.org/api/events.html)
