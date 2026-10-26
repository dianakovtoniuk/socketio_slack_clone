# socketio slack clone

A Socket.IO learning project that demonstrates namespaces and rooms, ending in a simple Slack-like chat clone.

## Features

- Main and `/admin` namespaces with rooms (`namespaces` demo)
- Slack-style chat with multiple namespaces (Wikipedia, Mozilla, Linux)
- Rooms inside each namespace with per-room message history
- Live room member count
- Real-time namespace updates (`/change-ns` demo route)

## Tech stack

- Node.js
- Express
- Socket.IO

## Project structure

```
.
├── .gitignore
├── package.json
├── namespaces/          # namespaces and rooms demo (port 8001)
│   ├── namespaces.js
│   └── public/
└── slackClone/          # Slack clone (port 9000)
    ├── slack.js
    ├── classes/         # Namespace and Room classes
    ├── data/            # seed namespaces and rooms
    └── public/          # client UI
```

## Getting started

```bash
npm install
```

### Run the namespaces demo

```bash
node namespaces/namespaces.js
```

Open http://localhost:8001/namespaces.html

### Run the Slack clone

```bash
node slackClone/slack.js
```

Open http://localhost:9000/slack.html

## Notes

- Authentication is stubbed out: the `io.use` middleware always calls `next()`, and the client uses a hardcoded username.
- Messages are stored in memory only and are lost when the server restarts.
- To see live namespace updates, open http://localhost:9000/change-ns while the chat is open.

