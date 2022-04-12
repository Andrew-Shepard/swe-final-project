```mermaid
sequenceDiagram
  actor U as user
  participant N as Local device
  participant M as Menu
  participant W as Web Service
  participant D as DB Cluster
U->>M: Open menu
M->>U: Return menu options
U->>M: Select edit
M->>U: Return edit ui
N->>W: Request edit with Auth token
W->>D: Change DB info
```