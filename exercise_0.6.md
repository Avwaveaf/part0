### Sequence Diagram: User interact with save buton in /spa 

[source](https://studies.cs.helsinki.fi/exampleapp/spa)

Below is a sequence diagram illustrating the interaction between browser and server when user submiting the entries in /spa ExampleApp:

```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    Note right of browser: with payload { "content": "fdsfds", "date": "2023-12-09T04:28:43.848Z" }
    activate server
    server-->>browser: Status code 201
    deactivate server
    Note left of server: Server responded with status of 201 (created) and giving response of JSON type {"message":"note created"}


```
