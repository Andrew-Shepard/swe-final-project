```mermaid
sequenceDiagram

  actor U as user
  participant N as NED Service
  participant R as Redis
  participant D as Database
  participant L as Location Service
  U->>N: request numbers
  activate N
  Note over N,D: Verify sender
  N->>R: check sender/destination country
  alt cache hit
    R-->>N: successful response
  else cache miss
    R-->>N: no data found
    N->>D: check sender/destination country
    D-->>N: result
    N-)R: save cache
  end
  Note over N,D: Verify recipient
  N->>R: check destination publickey
  alt cache hit
    R-->>N: successful response
  else cache miss
    R-->>N: no data found
    N->>L: check destination publickey
    L-->>N: result
    N-)R: save cache
  end
  Note over N,L: Send locations hash
  N->>L: send location hash
  L-->>N: 200 OK
  N-->>U: 200 OK
  deactivate N
```