title 0.4 New Note
    participant Browser
    participant Server

	Note over Browser: El usuario escribe algo en el Input y hace clic en submit // \n The user types something in the Input and clicks submit
    Browser->>Server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note
	Note over Server: El servidor añade la nota a la lista de notas // \n The Server adds the note to the notes list
    Server-->>Browser: redirect to /exampleapp/notes

    Browser->>Server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
    Server-->>Browser: HTML-code

    Browser->>Server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>Browser: main.css

    Browser->>Server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
    Server-->>Browser: main.js
    Note over Browser: El navegador comienza a ejecutar js-code que solicita datos JSON del servidor // \n Browser starts executing js-code that requests JSON data from Server
    
    Browser->>Server: https://studies.cs.helsinki.fi/exampleapp/data.json
    Server-->>Browser: [{"content": "pic420","date": "2023-10-09T11:05:12.139Z"}, ...]
    Note left of Browser: El navegador comienza a ejecuta el controlador de eventos que muestra las notas // \n The browser starts executing the event handler that displays the notes