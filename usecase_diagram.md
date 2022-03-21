```mermaid
graph TD;
    User-->a[Get current location numbers]-->b[Try to get numbers from local storage];
    User-->c[Get destination numbers]-->b;
    User-->d[Enter location manually];
    d-->b;
    b-->e[(Get numbers from the server)];
```