title 0.6 New Note SPA
    participant Browser
    participant Server

    Note left of Browser: Requisito previo: el navegador mostró la página exampleapp/spa \n y descargó todos los archivos necesarios (spa.js en particular)
	  
    Note left of Browser: Una función está vinculada al evento form.onsubmit, \n que crea una nueva nota, la envía a la variable de notas local, \n vuelve a dibujar las notas y finalmente envía la nota \n al servidor una vez que se envía el formulario.

    Note left of Browser: El usuario escribe algo en el campo de texto de la nota \n y hace clic en enviar, lo que activa el evento form.onsubmit

    Browser->>Server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    Server-->>Browser: Server responds with status code 201
	  
    Note right of Server: El servidor agrega una nota a la lista de notas

    Note left of Browser: spa.js verifica el código de estado, si está bien: \n imprime el mensaje de respuesta en la consola