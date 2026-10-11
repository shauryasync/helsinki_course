```mermaid
sequenceDiagram
autonumber
actor User
participant Browser
participant Server

    User->>Browser: Types note and clicks Save
    Note over Browser: JavaScript intercepts form submit,<br/>prevents default reload, creates new note object,<br/>and adds it locally to the notes array.
    Browser->>User: Renders the updated notes list on the page immediately
    Browser->>Server: HTTP POST /exampleapp/new_note_spa (JSON payload)
    Server-->>Browser: HTTP 201 Created (or status confirmation)
    Note over Browser: Server confirms save; no page reload needed.
```
