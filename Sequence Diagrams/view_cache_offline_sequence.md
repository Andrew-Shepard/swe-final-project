```mermaid
sequenceDiagram
  actor U as user
  participant N as Local device
  
U->>N: request location-based non-emergency numbers
  alt cache hit

    N-->>U: Phone has no internet state, return cache or none
  end

```