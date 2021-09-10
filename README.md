# TUTORIAL MSC

Date: September 9, 2021
Done: No

# PARA CORRER EL SERVIDOR

- [ ]  Clonar el repositorio

    ```bash
    git clone https://github.com/danieltibaquira/MSCTaller2Punto1.git
    ```

- [ ]  Moverse a la carpeta ***server***

    ```bash
    cd server/
    ```

- [ ]  Correr el servidor

    ```bash
    mvn clean install exec:java
    ```

- [ ]  Probar el servidor con el navegador o postman

    La ruta base es GET -  [http://localhost:8080/myapp/travel/](http://localhost:8080/myapp/travel/) para obtener todos los paseos

    Otras rutas son:

    - DELETE - [http://localhost:8080/myapp/travel/](http://localhost:8080/myapp/travel/){idPaseo}: para eliminar un paseo
    - PUT - [http://localhost:8080/myapp/travel/](http://localhost:8080/myapp/travel/){idPaseo}?paseoOrigin={nuevoOrigen}&paseoDest={nuevoDestino}
    - POST -  [http://localhost:8080/myapp/travel/](http://localhost:8080/myapp/travel/) crear un paseo con el body:

        ```bash
        {
        	"name":"nombre del paseo (String)",
        	"origin":"origen del paseo (String)",
        	"destination":"destino del paseo (String)",
        	"date":"fecha del paseo (String formato yyyy-mm-dd",
        	"id":"identificador del paseo (int)"
        }
        ```

    Todos los datos serán peristidos en una base MongoDB

# PARA CORRER EL CLIENTE JAVA

- [ ]  Moverse a la carpeta ***client***

    ```bash
    cd client/ 
    ```

- [ ]  Correr el cliente

    ```bash
    mvn clean install exec:java
    ```

- [ ]  Seguir los pasos del menú

# PARA CORRER EL CLIENTE MÓVIL

Instalar las dependencias globales

### NodeJS:

- Para MacOS:
    - Instalar [https://brew.sh](https://brew.sh/)
    - `brew install node@14`
- Para windows -- Seguir las instrucciones en [https://nodejs.dev](https://nodejs.dev/)
- Para Linux
    - Arch: yay -S nodejs-lts-fermium
    - Ubuntu: sudo apt install nodejs

### Expo-cli

Luego de instalar node

- `sudo npm install -g expo-cli`
- [ ]  Moverse a la carpeta ***client-rn***

    ```bash
    cd client-rn/ 
    ```

- [ ]  Instalar las dependencias del proyecto

    ```bash
    expo install
    ```

- [ ]  Correr el proyecto

    ```bash
    expo start --no-dev --minify
    ```

- [ ]  Abrir el simulador de iOS
- [ ]  En el proceso de expo tocar la tecla ***i***

### Si se desea correr en dispositivos android

Instalar **Ngrok**

- Seguir las instrucciones en [https://ngrok.com/download](https://ngrok.com/download)
- Alternativamente `sudo npm install -g ngrok`
- [ ]  Moverse a la carpeta ***server***

    ```bash
    cd server/
    ```

- [ ]  Crear el tunel

    ```bash
    ngrok http 8080
    ```

    - Genera un link del tipo [http://99fb-190-27-49-167.ngrok.io](http://99fb-190-27-49-167.ngrok.io/)
- [ ]  Abrir el proyecto **client-rn**
- [ ]  Abrir el archivo **/src/api/jersery.js**
- [ ]  Reemplazar la línea: `baseURL: 'http://localhost:8080/myapp/travel'` por: `baseURL: '{tunel creado por ngrok}'`
- [ ]  Correr el proyecto

    ```bash
    expo start --no-dev --minify
    ```

- [ ]  Abrir el simulador de Android
- [ ]  En el proceso de expo tocar la tecla ***a***
