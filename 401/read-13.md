# Reading 13: Message Queues

## Socket.IO Chat Example

**Resource:** [Socket.IO Chat Example](https://socket.io/get-started/chat/)

### 1. Explain to a non-technical recruiter what the Chat Example does.

The Socket.IO Chat Example demonstrates how users can send and receive messages instantly through a web application. When someone sends a message, the server broadcasts it to connected users without requiring them to refresh their browsers.

### 2. What proof of life are we getting on the backend?

- The server accepts client connections.
- The server receives chat messages through events.
- Messages are broadcast to connected clients.
- Server logs can confirm connections and activity.

### 3. What method sends an event to everyone?

`io.emit()` sends an event to all connected clients in the namespace, including the sender.

```javascript
io.emit('chat message', 'Hello everyone!');
```
(*sending a messgage or broadcasting, to everyone in the room*) (order placed or pickup) everyone who is *listening* will get that message

### 4. What flag sends a message to everyone except the emitting socket?

Use `socket.broadcast.emit()`.

```javascript
socket.broadcast.emit('chat message', 'Hello everyone!');      
```
(*everyone except this socket*)

---

## Rooms

**Resource:** [Socket.IO Rooms](https://socket.io/docs/v4/rooms/)

### 1. What is a room, and how is it useful?

A **room** is a server-side group of connected sockets. Rooms allow messages to be sent only to specific users instead of everyone.

Examples include private chat groups, multiplayer game sessions, and delivery updates.

### 2. How do you join and leave a room?

```javascript
socket.join('room1');  // Join
socket.leave('room1'); // Leave
```

Send a message to everyone in a room:

```javascript
io.to('room1').emit('message', 'Hello room!');
```

---

## Namespaces

**Resource:** [Socket.IO Namespaces](https://socket.io/docs/v4/namespaces/)

### 1. What is a namespace?

A **namespace** is a separate communication channel within a Socket.IO server. It allows different application features to manage their own connections and events.

### 2. Each namespace potentially has its own what?

1. **Event handlers**
2. **Rooms**
3. **Middleware**

### 3. Give an example of separate namespaces.

An online store could use:

- `/orders` — Handles customer orders.
- `/drivers` — Handles delivery updates.
- `/admin` — Handles administrative notifications.

Each namespace can have its own event listeners and access rules.

---
## Key Takeaway

Socket.IO enables real-time communication between clients and servers. **Rooms** organize connected users into groups, while **namespaces** separate communication channels for different application features.

Socket.IO events are not automatically persistent message queues. Additional storage or delivery mechanisms are needed when messages must survive disconnections.

## Bookmark and Review

- [Socket.IO Emit Cheatsheet](https://socket.io/docs/v4/emit-cheatsheet/)

