# Instrucciones
## Server
Para correr el servidor, desde la carpeta de taller 2 punto 1:

    `cd server
    mvn clean install exec:java`
  
  El servidor corre en `http://localhost:8080/myapp/`
  Las rutas definidas son:
  - `http://localhost:8080/myapp/travel/` con el método GET retorna todos los paseos en la base de datos
  - `http://localhost:8080/myapp/travel/{idPaseo}` con el método DELETE elimina el paseo con el id {IdPaseo}
  -`http://localhost:8080/myapp/travel/{idPaseo}?paseoOrigin={paseoOrigin}&paseoDest={paseoDest}` con el método PUT actualiza el Origen con {paseoOrigin} y el destino {paseoDest} para el paseo con el id {IdPaseo}
   -`http://localhost:8080/myapp/travel/?paseoOrigin={paseoOrigin}&paseoDest={paseoDest}&name={paseoName}&date={paseoDate}&id={paseoId}` con el método POST crea un paseo con Origen {paseoOrigin}, destino {paseoDest}, id {IdPaseo}, fecha {datePaseo} y nombre {namePaseo}
   
## Cliente Jersey

Para correr el cliente jersey, desde la carpeta de taller 2 punto 1:

    cd client
    mvn clean install exec:java
  Se mostrará un menú, escoja la acción a realizar y siga las instrucciones.

## Cliente React Native
Para correr el cliente react native, desde la carpeta de taller 2 punto 1:
Instalar las dependencias globales

NodeJS:
- Para MacOS:
-- Instalar https://brew.sh
-- `brew install node@14`
- Para windows
-- Seguir las instrucciones en https://nodejs.dev
- Para Linux
-- Arch: yay -S nodejs-lts-fermium
-- Ubuntu: sudo apt install nodejs

Expo-cli
- `sudo npm install -g expo-cli`

Ahora, nos movemos a la carpeta del proyecto:

    cd client-rn
Instalamos las dependencias

    expo install
Corremos el proyecto

    expo start --no-dev --minify
Si deseamos correr el proyecto en un emulador de iOS presionar la letra ***i***
Si deseamos correr el proyecto en un emulador de Android se debe iniciar con el siguiente comando

    emulator @<nombre_del_emulador> -dns-server 8.8.8.8
Luego presionar la letra ***a***
