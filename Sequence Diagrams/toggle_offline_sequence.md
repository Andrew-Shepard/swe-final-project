```mermaid
sequenceDiagram
  actor U as user
  participant N as Local device
  participant M as Menu
U->>M: Open menu
M->>U: Return menu options
U->>M: Select offline
M->>N: Set application state to offline
  alt cache hit
    N-->>U: Does not check state, return cache or none
  end
```