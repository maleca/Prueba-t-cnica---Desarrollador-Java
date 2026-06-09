Esta guía se divide en tres partes principales.

1. La primera parte trata sobre la instalación de la base de datos MySQL, MySQL Workbench y la ejecución de los scripts SQL necesarios para el proyecto de comercio electrónico.

2. La segunda parte trata sobre la ejecución de la aplicación de comercio electrónico Spring Boot.

3. La tercera parte trata sobre la ejecución de la aplicación de comercio electrónico con Angular Frontend.

**Ejecución del servidor MySQL:**
1. Descargue el código fuente adjunto a la lección 217 y extraiga el directorio del archivo ZIP.

2. Abra el directorio `01-starter-files`. Ejecute los scripts que se encuentran en el directorio `01-starter-files/db-scripts`. Para ejecutar estos scripts y ver los resultados posteriormente, debe instalar un cliente MySQL en su equipo. Por lo tanto, instalaremos MySQL Workbench.

3. Instale [choco](https://chocolatey.org/install). choco es un gestor de paquetes destacado para Windows. Nota: Asegúrese de abrir Windows PowerShell como administrador para todas las instalaciones de software.

<img src="screenshots/Screenshot (1).png"/>
4. Descargue el servidor MySQL Community desde PowerShell usando `choco install mysql`. Nota: Al instalar el software con choco, acepte ejecutar todos los scripts presionando `A`.

<img src="screenshots/Screenshot (4).png"/>
5. Puede iniciar MySQL de la siguiente manera: presione `tecla de Windows + R`

<img src="screenshots/Screenshot (11).png"/>
6. Una vez en `Servicios`, busque `MySQL` e inícielo.

<img src="screenshots/Screenshot (13).png"/>
7. Ahora, para ejecutar los scripts SQL de inicio en `01-starter-files/db-scripts`, instalemos MySQL Workbench. Descarga MySQL Workbench con `choco install mysql.workbench`. Deberías ver MySQL WB al iniciar Windows. Para ejecutar todos los scripts, ábrelos uno por uno y ejecútalos haciendo clic en el icono ⚡️.

<img src="screenshots/Screenshot (7).png"/>

<img src="screenshots/Screenshot (8).png"/>

**Ejecutando la aplicación Spring Boot:**
1. Instala JDK en tu máquina desde PowerShell con `choco install zulu11`. Abre la línea de comandos y ejecuta `java --version` para ver la versión de Java.

<img src="screenshots/Screenshot (9).png"/>
2. Configura JAVA_HOME (como administrador) desde la línea de comandos con `setx -m JAVA_HOME "C:\Program Files\Zulu\zulu-11"`. Si instalaste Java usando Choco, debería estar instalado en la ruta especificada anteriormente. De lo contrario, asegúrate de tener la ruta correcta al JDK. Para comprobar si la ruta es correcta, ejecuta `refreshenv` en la misma línea de comandos y luego `echo %JAVA_HOME%`. Esto te mostrará la ruta que acabas de configurar.

3. Ahora, accede a `02-backend/spring-boot-ecommerce` con `cd`. Una vez dentro, cambia la versión de Java a 11 en el archivo pom.xml. Esto se debe a que instalamos Java 11 anteriormente. No podemos instalar la distribución Java 13 usando Choco (probablemente porque Java 13 no es LTS). Ahora, ejecuta `mvnw clean install`. Esto puede tardar un par de minutos.

4. Una vez que todo haya salido bien en el paso 3, para iniciar tu aplicación ejecuta `.mvnw spring-boot:run`. Esto ejecutará tu aplicación backend. Una vez que tu aplicación esté lista, accede a `http://localhost:8080/api/` en tu navegador y deberías ver algo similar a lo siguiente: (Nota: Asegúrate de que tu servidor MySQL esté activo).

<img src="screenshots/Screen Shot 2022-07-17 at 4.13.18 PM.png" />

**Ejecutando la aplicación Angular:**
1. Instala Node.js en tu máquina usando Choco. `choco install nodejs-lts`. Esto instalará Node.js v16 (lts).

2. Ejecutando `node -v` y `npm -v` en la línea de comandos, obtendrás sus respectivos números de versión.

3. Instala la CLI de Angular globalmente desde la línea de comandos ejecutando: `npm install -g @angular/cli`. `ng version` te mostrará el número de versión de la CLI de Angular. 4. Ahora, navega a nuestra aplicación front-end en `03-frontend/angular-ecommerce`. Una vez dentro del directorio `angular-ecommerce`, ejecuta `npm install`.

5. Ahora, ejecuta `ng build` (esto puede tardar un par de minutos) y luego `ng serve`.

6. Deberías tener la aplicación front-end de comercio electrónico funcionando en `http://localhost:4200`.

Con esto, deberías tener una aplicación de comercio electrónico completamente funcional ejecutándose en tu máquina.

<img src="screenshots/Screenshot (15).png"/>
