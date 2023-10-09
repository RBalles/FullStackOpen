title 0.5 SPA
    participant Browser
    participant Server

    Browser->>Server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa
    Server-->>Browser: HTML-code

    Browser->>Server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>Browser: main.css

    Browser->>Server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    Server-->>Browser: spa.js

    Note over Browser: El navegador comienza a ejecutar js-code que solicita datos JSON del servidor // \n Browser starts executing js-code that requests JSON data from Server

    Browser->>Server: https://studies.cs.helsinki.fi/exampleapp/data.json
    Server-->>Browser: [{"content": "pic420","date": "2023-10-09T11:05:12.139Z"}, ...]
    Note left of Browser: El navegador comienza a ejecuta el controlador de eventos que muestra las notas // \n The browser starts executing the event handler that displays the notes
