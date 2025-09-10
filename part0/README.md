# Part 0 Exercises

## 0.4: New note diagram

```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate Server
    Server-->>Browser: HTML document
    deactivate Server

    Browser->>Server: GET /main.css
    Server-->>Browser: CSS file

    Browser->>Server: GET /main.js
    Server-->>Browser: JavaScript file

    Note right of Browser: Browser executes JavaScript code that fetches notes

    Browser->>Server: GET /data.json
    Server-->>Browser: JSON [{content: "HTML is easy", date: "2023-01-01"}, ... ]

    Note right of Browser: Browser executes callback to render notes
