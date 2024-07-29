::: mermaid
sequenceDiagram
participant browser
participant server

note over browser: form button clicked

browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
activate server
note over server: > Access POST data <br/> > Create new note object <br/> > adds it to "notes" array
server-->>browser: redirect to /exampleapp/notes
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
activate server
server-->>browser: HTML document
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate server
server-->>browser: the css file
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
activate server
server-->>browser: the JavaScript file
deactivate server

 Note over browser: >execute JS file<br/> >fetch JSON data

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate server
server-->>browser: [{ "content": "654684", "date": "2024-07-23" }, ... ]
deactivate server

Note over browser: >execute callback function <br/> >render notes
:::