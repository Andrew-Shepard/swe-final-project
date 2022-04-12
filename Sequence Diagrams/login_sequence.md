```mermaid
sequenceDiagram
  actor U as user
  participant N as Local device
  participant M as Menu
  participant W as Web Service
  participant D as DB Cluster
U->>M: Open menu
M->>U: Return menu options
U->>M: Select login
M->>U: Return login ui
U->>W: Provide credentials
W->>D: User lookup
W->>N: Generate Temp Auth token
```