### Sequence Diagram: User First Enter the /spa 

[source](https://studies.cs.helsinki.fi/exampleapp/spa)

Below is a sequence diagram illustrating the interaction between browser and server when user entering /spa ExampleApp:

```mermaid
sequenceDiagram
    participant browser
    participant server

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

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "123456789", "date": "2023-12-08T20:00:22.107Z" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes

