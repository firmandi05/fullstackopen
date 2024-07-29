::: mermaid
sequenceDiagram
  participant browser as browser
  participant server as server

  Note over browser: *save button clicked* <br/> >prevent default form handling <br/> >create new note object <br/> >Add's new note to notes list <br/> >rerender the note list
  browser ->>+ server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
  Note over server: *read's POST body* <br/> >update notes list
:::