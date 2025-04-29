Got it! Let's create UML sequence diagrams for each method, incorporating both API calls and socket interactions. The user will interact with the server via APIs for user creation and settings, while other operations will use sockets.

### 1. `initialize`

```mermaid
sequenceDiagram
    participant User
    participant Server
    participant Database
    Server->>Database: countDocuments(User)
    alt No users
        Server->>Database: save(defaultUser)
    end
```

### 2. `newUser`

```mermaid
sequenceDiagram
    participant User
    participant Server (API)
    participant Database
    User->>Server (API): newUser(username, pfpUrl)
    Server (API)->>Database: findOne(User, {username})
    alt User exists
        Server (API)-->>User: return -1
    else User does not exist
        Server (API)->>Database: save(newUser)
        Server (API)-->>User: return newUser._id
    end
```

### 3. `createSession`

```mermaid
sequenceDiagram
    participant User
    participant Server (API)
    participant Database
    User->>Server (API): createSession(code)
    Server (API)->>Database: save(newSession)
    Server (API)-->>User: return newSession._id
```

### 4. `joinSession`

```mermaid
sequenceDiagram
    participant User
    participant Server (Socket)
    participant Database
    User->>Server (Socket): joinSession(userId, session_id)
    Server (Socket)->>Database: isValid(session_id)
    alt Invalid session_id
        Server (Socket)-->>User: throw Error
    else Valid session_id
        Server (Socket)->>Database: findOne(UserSession, {user_id, session_id})
        alt UserSession exists
            Server (Socket)-->>User: End
        else UserSession does not exist
            Server (Socket)->>Database: save(userSession)
        end
    end
```

### 5. `addAdmin`

```mermaid
sequenceDiagram
    participant User
    participant Server (Socket)
    participant Database
    User->>Server (Socket): addAdmin(userId, sessionId)
    Server (Socket)->>Database: updateOne(UserSession, {user_id, session_id}, {$set: {is_admin: true}})
```

### 6. `removeAdmin`

```mermaid
sequenceDiagram
    participant User
    participant Server (Socket)
    participant Database
    User->>Server (Socket): removeAdmin(userId, sessionId)
    Server (Socket)->>Database: updateOne(UserSession, {user_id, session_id}, {$set: {is_admin: false}})
```

### 7. `joinOrCreateSession`

```mermaid
sequenceDiagram
    participant User
    participant Server (API)
    participant Server (Socket)
    participant Database
    User->>Server (API): joinOrCreateSession(username, code)
    Server (API)->>Database: newUser(username)
    Server (API)->>Database: findOne(Session, {code})
    alt Session exists
        Server (API)->>Server (Socket): joinSession(userId, session._id)
    else Session does not exist
        Server (API)->>Database: createSession(code)
        Server (API)->>Database: addAdmin(userId, newSession._id)
        Server (API)->>Server (Socket): joinSession(userId, newSession._id)
    end
    Server (API)-->>User: return {sessionId, userId}
```

### 8. `sendMessage`

```mermaid
sequenceDiagram
    participant User
    participant Server (Socket)
    participant Database
    User->>Server (Socket): sendMessage(userId, sessionId, content, fileUrl, messageType)
    Server (Socket)->>Database: save(message)
```

### 9. `getMessage`

```mermaid
sequenceDiagram
    participant User
    participant Server (Socket)
    participant Database
    User->>Server (Socket): getMessage(sessionId, limit)
    Server (Socket)->>Database: find(Message, {session_id})
    Database->>Database: sort({timestamp: -1})
    Database->>Database: limit(limit)
    Database->>Database: populate('user_id', 'username')
    Server (Socket)-->>User: return messages
```

### 10. `updateSessionSettings`

```mermaid
sequenceDiagram
    participant User
    participant Server (API)
    participant Database
    User->>Server (API): updateSessionSettings(sessionId, newSettings)
    Server (API)->>Database: updateOne(Session, {_id: sessionId}, {$set: {session_settings: newSettings}})
```

### 11. `editMessage`

```mermaid
sequenceDiagram
    participant User
    participant Server (Socket)
    participant Database
    User->>Server (Socket): editMessage(messageId, newContent)
    Server (Socket)->>Database: updateOne(Message, {_id: messageId}, {$set: {content: newContent}})
```

### 12. `deleteMessage`

```mermaid
sequenceDiagram
    participant User
    participant Server (Socket)
    participant Database
    User->>Server (Socket): deleteMessage(messageId)
    Server (Socket)->>Database: deleteOne(Message, {_id: messageId})
```

### 13. `checkMessage`

```mermaid
sequenceDiagram
    participant User
    participant Server (Socket)
    participant Database
    User->>Server (Socket): checkMessage(messageId, sessionId)
    Server (Socket)->>Database: findOne(Message, {_id: messageId, session_id})
    alt Message exists
        Server (Socket)-->>User: return true
    else Message does not exist
        Server (Socket)-->>User: return false
    end
```

### 14. `checkSession`

```mermaid
sequenceDiagram
    participant User
    participant Server (API)
    participant Database
    User->>Server (API): checkSession(sessionCode)
    Server (API)->>Database: findOne(Session, {code: sessionCode})
    alt Session exists
        Server (API)-->>User: return session._id
    else Session does not exist
        Server (API)-->>User: return false
    end
```

These UML sequence diagrams illustrate the interactions between the user, server (via API or sockets), and the database for each method, showing how different operations are handled using APIs and sockets.