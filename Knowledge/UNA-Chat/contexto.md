# Contexto de UNA Chat

## Propósito

UNA Chat es una aplicación académica de chat en tiempo real de la Universidad Nacional. Permite intercambiar texto y enlaces multimedia validados de forma segura.

## Ubicación y arquitectura verificadas

- Repositorio independiente: `Repos/Lab5-Paradigmas/`.
- Aplicación vigente: `Repos/Lab5-Paradigmas/despues/`.
- Servidor monolítico CommonJS con Node.js 22, Express 4 y Socket.IO 4.
- Cliente HTML/CSS/JavaScript servido por Express; no usa React, NestJS ni TypeScript.
- Entrada del servidor: `despues/server.js`; interfaz: `despues/index.html`.
- Puerto local predeterminado: `3000`.

## Autenticación

El Laboratorio 8 incorpora Auth0 con OAuth 2.0/OpenID Connect mediante el SDK oficial `express-openid-connect`. La identidad reside en una cookie de sesión cifrada y firmada. La ruta del chat, `/api/me` y el handshake de Socket.IO exigen una sesión válida. El nombre de los mensajes se obtiene de esa identidad en el servidor.

## Ejecución

Desde `Repos/Lab5-Paradigmas/despues/`: copiar `.env.example` a `.env`, completar Auth0, ejecutar `npm install` y `npm start`. Consultar el README del repositorio para URLs y pruebas.

## Estado y pendientes externos

- Código Auth0 y protección del chat implementados.
- Pendiente crear/configurar la aplicación Auth0 y habilitar Google con credenciales del estudiante.
- Pendiente adaptar el servidor monolítico a Vercel Functions/Services. Vercel ya admite WebSockets, pero UNA Chat conserva conexiones y difusión en memoria; para varias instancias necesita un endpoint compatible y coordinación compartida (por ejemplo Redis).
- Pendiente recibir `obsidian-brain-instructions 1.md`; esta nota de contexto no pretende sustituir la memoria exigida por ese archivo.
