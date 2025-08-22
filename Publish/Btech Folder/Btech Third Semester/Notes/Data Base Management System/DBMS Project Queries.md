### Database Design Recommendations

Your design is close to being functional but could benefit from a few adjustments for enhanced normalization, flexibility, and ease of query. Here are some suggestions:

1. **Sessions Table Enhancements:**
   - **Primary Key Change**: Since `session_code` is unique, it can serve as the primary key directly. This avoids needing an additional serial ID.
   - **Separate Join Tables for Many-to-Many Relationships**:
     - Move `usernames` and `admins` into separate join tables, e.g., `session_users` and `session_admins`, with references to both session and user tables.
   - **User Tokens**: `user_tokens` should ideally be its own table to maintain a normalized design. It would contain a token reference and a foreign key reference to the user ID.

2. **Messages Table Enhancements:**
   - Reference the `session_code` directly in `messages` instead of a numeric `session_id` for simplicity.

3. **Settings Table Enhancement:**
   - Instead of combining session-related settings directly into the sessions table, this design allows optional settings for each session, which can be set or left as defaults.

4. **Separate Users Table**:
   - Consider adding a `users` table to maintain unique users across sessions.

### Improved Table Schema

Here’s a possible structure that builds on your idea:

```sql
CREATE TABLE IF NOT EXISTS sessions (
    session_code VARCHAR(255) PRIMARY KEY,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE IF NOT EXISTS users (
    user_id SERIAL PRIMARY KEY,
    username VARCHAR(255) UNIQUE NOT NULL
);

CREATE TABLE IF NOT EXISTS user_tokens (
    token_id SERIAL PRIMARY KEY,
    token VARCHAR(255) NOT NULL,
    user_id INTEGER REFERENCES users(user_id) ON DELETE CASCADE
);

CREATE TABLE IF NOT EXISTS session_users (
    session_code VARCHAR(255) REFERENCES sessions(session_code) ON DELETE CASCADE,
    user_id INTEGER REFERENCES users(user_id) ON DELETE CASCADE,
    PRIMARY KEY (session_code, user_id)
);

CREATE TABLE IF NOT EXISTS session_admins (
    session_code VARCHAR(255) REFERENCES sessions(session_code) ON DELETE CASCADE,
    user_id INTEGER REFERENCES users(user_id) ON DELETE CASCADE,
    PRIMARY KEY (session_code, user_id)
);

CREATE TABLE IF NOT EXISTS messages (
    message_id SERIAL PRIMARY KEY,
    session_code VARCHAR(255) REFERENCES sessions(session_code) ON DELETE CASCADE,
    user_id INTEGER REFERENCES users(user_id) ON DELETE SET NULL,
    message_content TEXT NOT NULL,
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE IF NOT EXISTS settings (
    session_code VARCHAR(255) PRIMARY KEY REFERENCES sessions(session_code),
    attachments BOOLEAN DEFAULT TRUE,
    max_members INTEGER DEFAULT 10
);

-- Indexes for optimized queries
CREATE INDEX IF NOT EXISTS idx_session_code_messages ON messages(session_code);
CREATE INDEX IF NOT EXISTS idx_session_code_users ON session_users(session_code);
```

### Updated Functions

Below are updated versions of each function, based on the improved schema.

```javascript
const { Pool } = require('pg');
const pool = new Pool({
    user: 'postgres',
    host: 'localhost',
    database: 'comms',
    password: 'root',
    port: 5432
});

let isInitialized = false;

async function initialize() {
    if (isInitialized) {
        console.log('Database is already initialized.');
        return;
    }
    try {
        await pool.query(initializer);
        isInitialized = true;
        console.log('Database initialized successfully.');
    } catch (err) {
        console.error('Error initializing database:', err);
    }
}

// Check if a session with a given code exists
async function checkSessionCode(sessionCode) {
    const res = await pool.query('SELECT 1 FROM sessions WHERE session_code = $1', [sessionCode]);
    return res.rows.length > 0;
}

// Create a new session and add initial admin
async function createSession(sessionCode, username) {
    await pool.query('INSERT INTO sessions (session_code) VALUES ($1)', [sessionCode]);
    const user = await addUser(username);
    await addAdmin(sessionCode, user.user_id);
    return { sessionCode, admin: user.username };
}

// Add an admin to a session
async function addAdmin(sessionCode, userId) {
    const res = await pool.query(
        'INSERT INTO session_admins (session_code, user_id) VALUES ($1, $2) RETURNING *',
        [sessionCode, userId]
    );
    return res.rows[0];
}

// Remove an admin from a session
async function removeAdmin(sessionCode, userId) {
    const res = await pool.query(
        'DELETE FROM session_admins WHERE session_code = $1 AND user_id = $2 RETURNING *',
        [sessionCode, userId]
    );
    return res.rowCount > 0;
}

// Get all admins of a session
async function getAdmins(sessionCode) {
    const res = await pool.query(
        'SELECT u.username FROM session_admins sa JOIN users u ON sa.user_id = u.user_id WHERE sa.session_code = $1',
        [sessionCode]
    );
    return res.rows.map(row => row.username);
}

// Add a user to a session
async function addUserToSession(sessionCode, username) {
    const user = await addUser(username);
    await pool.query(
        'INSERT INTO session_users (session_code, user_id) VALUES ($1, $2) ON CONFLICT DO NOTHING',
        [sessionCode, user.user_id]
    );
    return { sessionCode, username };
}

// Add a new user
async function addUser(username) {
    const res = await pool.query(
        'INSERT INTO users (username) VALUES ($1) ON CONFLICT (username) DO UPDATE SET username = EXCLUDED.username RETURNING *',
        [username]
    );
    return res.rows[0];
}

// Add a message to a session
async function addMessage(sessionCode, userId, content) {
    const res = await pool.query(
        'INSERT INTO messages (session_code, user_id, message_content) VALUES ($1, $2, $3) RETURNING *',
        [sessionCode, userId, content]
    );
    return res.rows[0];
}

// Retrieve all messages for a session
async function getMessages(sessionCode) {
    const res = await pool.query(
        'SELECT m.*, u.username FROM messages m JOIN users u ON m.user_id = u.user_id WHERE m.session_code = $1 ORDER BY m.timestamp',
        [sessionCode]
    );
    return res.rows;
}

// Create or update settings for a session
async function upsertSettings(sessionCode, attachments, maxMembers) {
    const res = await pool.query(
        `INSERT INTO settings (session_code, attachments, max_members)
        VALUES ($1, $2, $3)
        ON CONFLICT (session_code) DO UPDATE SET attachments = EXCLUDED.attachments, max_members = EXCLUDED.max_members RETURNING *`,
        [sessionCode, attachments, maxMembers]
    );
    return res.rows[0];
}

// Get session settings
async function getSettings(sessionCode) {
    const res = await pool.query('SELECT * FROM settings WHERE session_code = $1', [sessionCode]);
    return res.rows[0];
}

module.exports = {
    initialize,
    checkSessionCode,
    createSession,
    addAdmin,
    removeAdmin,
    getAdmins,
    addUserToSession,
    addMessage,
    getMessages,
    upsertSettings,
    getSettings
};
```

### Summary of Changes
- `sessions` table now uses `session_code` as the primary key.
- `session_users` and `session_admins` handle many-to-many relationships.
- `users` table manages unique usernames.
- `settings` is stored in its table, simplifying session configuration.
- Functions are updated to accommodate the modified schema.

This setup will give you more flexibility, reduce redundancy, and make managing sessions and users simpler and more robust.




