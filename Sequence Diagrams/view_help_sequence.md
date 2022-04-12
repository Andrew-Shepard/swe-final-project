```mermaid
sequenceDiagram
  actor U as user
  participant N as Local device
  participant M as Menu
U->>M: Open menu
M->>U: Return menu options
U->>M: Select help
M->>U: Return help ui
```