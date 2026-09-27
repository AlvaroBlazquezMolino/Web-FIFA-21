# SPANISH

# Web FIFA 21
Proyecto web realizado para trabajar con una base de datos de FIFA 21.
La página permite consultar y gestionar parte de la información
almacenada en MySQL, además de realizar diferentes consultas sobre
jugadores.

## Requisitos

Para ejecutar el proyecto se necesita:

-   **XAMPP**, que incluye Apache, PHP, MySQL y phpMyAdmin.
-   Un navegador web.
-   Conexión a Internet para cargar algunas librerías que utiliza la
    página.

No es necesario instalar Node.js, Composer ni ningún otro programa
adicional.

------------------------------------------------------------------------

## 1. Instalar XAMPP

Descarga e instala XAMPP desde su página oficial:

https://www.apachefriends.org/

Durante la instalación puedes dejar las opciones habituales.

Una vez instalado, abre el **XAMPP Control Panel**.

------------------------------------------------------------------------

## 2. Copiar el proyecto a XAMPP

Copia la carpeta del proyecto dentro de la carpeta `htdocs` de XAMPP.

Por ejemplo:

``` text
C:\xampp\htdocs\Fifa\
```

Dentro de esa carpeta deberían aparecer directamente archivos como:

``` text
Web FIFA 21.html
conexion.php
FIFAconInserc.sql
Club.js
Entrenador.js
tabla.js
...
```

La carpeta `img` también debe estar dentro de `Fifa`:

``` text
C:\xampp\htdocs\Fifa\img\
```

No abras el archivo HTML haciendo doble clic sobre él. El proyecto
utiliza PHP y peticiones AJAX, por lo que debe ejecutarse a través de
Apache.

------------------------------------------------------------------------

## 3. Iniciar Apache y MySQL

Abre el **XAMPP Control Panel** y pulsa:

-   `Start` en **Apache**
-   `Start` en **MySQL**

Los dos servicios deben aparecer como iniciados.

Si Apache o MySQL no se pueden iniciar porque sus puertos están
ocupados, habrá que solucionar ese conflicto de puertos antes de
continuar.

------------------------------------------------------------------------

## 4. Crear e importar la base de datos

El proyecto utiliza una base de datos MySQL llamada:

``` text
Fifa
```

El archivo que contiene la estructura y los datos iniciales es:

``` text
FIFAconInserc.sql
```

### Importarla mediante phpMyAdmin

Con Apache y MySQL iniciados:

1.  Abre en el navegador: `http://localhost/phpmyadmin/`
2.  Entra en la pestaña **Importar**.
3.  Selecciona el archivo `FIFAconInserc.sql`.
4.  Pulsa **Importar** o **Continuar**.
5.  Comprueba que aparece la base de datos `Fifa`.

El propio archivo SQL crea la base de datos si todavía no existe, así
que no es necesario crearla manualmente.

### Si ya tienes la base de datos

Si ya habías importado `FIFAconInserc.sql` anteriormente y la base de
datos `Fifa` funciona correctamente, no es necesario volver a
importarla.

------------------------------------------------------------------------

## 5. Configuración de la conexión

El archivo:

``` text
conexion.php
```

es el encargado de conectar la página con MySQL.

La configuración incluida por defecto es:

``` text
Servidor: localhost
Base de datos: Fifa
Usuario: root
Contraseña: vacía
```

Esta es la configuración habitual de MySQL en una instalación estándar
de XAMPP.

Si has cambiado la contraseña del usuario `root` o utilizas una
configuración diferente, tendrás que modificar `conexion.php` con tus
propios datos de acceso.

------------------------------------------------------------------------

## 6. Abrir la página

Con Apache y MySQL funcionando, abre:

``` text
http://localhost/Fifa/Web%20FIFA%2021.html
```

También puedes escribir:

``` text
http://localhost/Fifa/
```

y seleccionar `Web FIFA 21.html` si el servidor muestra el contenido de
la carpeta.

**Importante:** no ejecutar el HTML directamente desde Windows. Debe
aparecer una dirección que empiece por `http://localhost/`.

------------------------------------------------------------------------

## 7. ¿Qué se puede hacer en la web?

La página está dividida en varias secciones.

### Inicio

Muestra la página principal del proyecto y las imágenes relacionadas con
FIFA 21.

### Tablas

Desde el menú **TABLAS** se puede acceder a:

-   **Estadio**
-   **Club**
-   **Entrenador**

En estas secciones se pueden consultar los registros almacenados en
MySQL y, según la sección, insertar, modificar y eliminar registros.

Los cambios realizados desde la página se guardan directamente en la
base de datos.

### Registros

La sección **REGISTROS** permite seleccionar diferentes consultas de la
base de datos:

-   Jugadores
-   Estilos
-   Jugadores con 5 estrellas de skill
-   Links verdes

La opción de **Nominados** aparece en el menú como ejemplo de mensaje
devuelto por la web cuando no hay consulta a devolver.

------------------------------------------------------------------------

## 8. Librerías utilizadas

La página utiliza varias librerías JavaScript y CSS externas, cargadas
directamente desde Internet:

-   jQuery
-   Bootstrap 4
-   Popper.js
-   DataTables

Por este motivo, para que la página se vea y funcione exactamente como
está planteada, es recomendable tener conexión a Internet mientras se
ejecuta.

No hay que instalar estas librerías manualmente.

------------------------------------------------------------------------

## 9. Estructura del proyecto

La carpeta principal contiene, entre otros, los siguientes archivos:

``` text
Fifa/
│
├── Web FIFA 21.html
├── conexion.php
├── FIFAconInserc.sql
│
├── Club.js
├── Entrenador.js
├── Desp.js
├── tabla.js
│
├── procesa4.php
├── procesaCLUB.php
├── procesaENTRENADOR.php
├── procesaESTADIO.php
├── procesaTABLA.php
│
└── img/
    ├── 76GameBanner.jpg
    ├── FIA-21.png
    ├── fifa.jpeg
    ├── estadio.jpg
    ├── liga.jpg
    ├── champions.jpg
    └── premier.jpg
```

Los archivos `procesa*.php` reciben las peticiones de la página y
realizan las operaciones correspondientes sobre MySQL.

Los archivos `.js` se encargan principalmente de la interacción de la
página con esos archivos PHP y de mostrar los resultados en tablas.

------------------------------------------------------------------------

## 10. Solución rápida de problemas

### La página no carga

Comprueba que **Apache está iniciado** en XAMPP y que estás entrando
mediante `localhost`.

### Aparece un error relacionado con MySQL

Comprueba que **MySQL está iniciado** y que existe la base de datos
`Fifa`.

También puedes comprobar la conexión desde phpMyAdmin:

``` text
http://localhost/phpmyadmin/
```

### Las tablas aparecen vacías

Comprueba que `FIFAconInserc.sql` se ha importado correctamente y que la
base de datos `Fifa` contiene las tablas y los datos.

### Los estilos o las tablas no se muestran correctamente

Comprueba que tienes conexión a Internet, ya que Bootstrap, jQuery,
Popper.js y DataTables se cargan desde servidores externos.

### Al hacer doble clic en el HTML no funciona

Es normal. El proyecto utiliza PHP y MySQL.

Hay que iniciar Apache y abrir la página mediante una dirección como:

``` text
http://localhost/Fifa/Web%20FIFA%2021.html
```

------------------------------------------------------------------------

## 11. Para ejecutar el proyecto después de instalarlo

Una vez realizada la configuración inicial, cada vez que quieras
utilizar la web solo necesitas:

1.  Abrir XAMPP.
2.  Iniciar **Apache**.
3.  Iniciar **MySQL**.
4.  Abrir en el navegador:

``` text
http://localhost/Fifa/Web%20FIFA%2021.html
```

No es necesario volver a importar la base de datos cada vez.

------------------------------------------------------------------------

## Nota para GitHub

Si descargas este proyecto desde GitHub, recuerda que GitHub solo
almacena los archivos del proyecto. **XAMPP y MySQL no forman parte del
repositorio**, por lo que cada persona que quiera ejecutarlo en su
ordenador tendrá que instalar XAMPP y realizar la configuración indicada
anteriormente.

También es importante mantener la estructura de carpetas del proyecto,
especialmente la carpeta `img`, ya que el HTML utiliza rutas relativas
para cargar las imágenes.


# ENGLISH

# Web FIFA 21

Web project developed to work with a FIFA 21 database. The website allows users to view and manage part of the information stored in MySQL, as well as perform different queries related to players and chemistry.

## Requirements

To run the project, you need:

* **XAMPP**, which includes Apache, PHP, MySQL and phpMyAdmin.
* A web browser (Chrome, Firefox, Edge, etc.).
* An Internet connection to load some of the libraries used by the website from their CDNs.

You do not need to install Node.js, Composer or any other additional software.

---

## 1. Install XAMPP

Download and install XAMPP from its official website:

https://www.apachefriends.org/

You can leave the default installation options.

Once installed, open the **XAMPP Control Panel**.

---

## 2. Copy the project to XAMPP

Copy the project folder into XAMPP's `htdocs` directory.

For example:

```
C:\xampp\htdocs\Fifa\
```

The folder should directly contain files such as:

```
Web FIFA 21.html
conexion.php
FIFAconInserc.sql
Club.js
Entrenador.js
tabla.js
...
```

The `img` folder should also be inside the `Fifa` folder:

```
C:\xampp\htdocs\Fifa\img\
```

Do not open the HTML file by double-clicking it. The project uses PHP and AJAX requests, so it needs to be served through Apache.

---

## 3. Start Apache and MySQL

Open the **XAMPP Control Panel** and click:

* `Start` for **Apache**
* `Start` for **MySQL**

Both services should appear as running.

If Apache or MySQL cannot be started because their ports are already in use, you will need to resolve the port conflict before continuing.

---

## 4. Create and import the database

The project uses a MySQL database called:

```
Fifa
```

The file containing the database structure and initial data is:

```
FIFAconInserc.sql
```

### Importing it using phpMyAdmin

With Apache and MySQL running:

1. Open `http://localhost/phpmyadmin/`
2. Go to the **Import** tab.
3. Select the `FIFAconInserc.sql` file.
4. Click **Import** or **Go**.
5. Check that the `Fifa` database appears.

The SQL file creates the database if it does not already exist, so there is no need to create it manually.

### If you already have the database

If you have already imported `FIFAconInserc.sql` and the `Fifa` database is working correctly, you do not need to import it again.

---

## 5. Database connection configuration

The file:

```
conexion.php
```

is responsible for connecting the website to MySQL.

The default configuration is:

```
Server: localhost
Database: Fifa
Username: root
Password: empty
```

This is the usual configuration for a standard XAMPP installation.

If you have changed the password of the `root` user or use a different MySQL configuration, you will need to modify `conexion.php` with your own connection details.

---

## 6. Open the website

With Apache and MySQL running, open:

```
http://localhost/Fifa/Web%20FIFA%2021.html
```

You can also open:

```
http://localhost/Fifa/
```

and select `Web FIFA 21.html` if the server displays the contents of the folder.

**Important:** do not run the HTML file directly from Windows. The address in your browser should start with `http://localhost/`.

---

## 7. What can you do on the website?

The website is divided into several sections.

### Home

Displays the main page of the project and FIFA 21-related images.

### Tables

From the **TABLES** menu you can access:

* **Stadium**
* **Club**
* **Manager**

These sections allow you to view records stored in MySQL and, depending on the section, insert, modify and delete records.

Changes made through the website are saved directly to the database.

### Records

The **RECORDS** section allows you to select different database queries:

* Players
* Styles
* Players with 5-star skill moves
* Green links

The **Nominees** option is included in the menu because it was part of the original design, but the surviving database does not contain the table or relationship required for this query. Therefore, this option could not be faithfully reconstructed from the available files.

---

## 8. Libraries used

The website uses several external JavaScript and CSS libraries loaded directly from CDNs:

* jQuery
* Bootstrap 4
* Popper.js
* DataTables

For this reason, an Internet connection is recommended while running the website so that the page can load and display correctly.

There is no need to install these libraries manually.

---

## 9. Project structure

The main project folder contains, among others, the following files:

```
Fifa/
│
├── Web FIFA 21.html
├── conexion.php
├── FIFAconInserc.sql
│
├── Club.js
├── Entrenador.js
├── Desp.js
├── tabla.js
│
├── procesa4.php
├── procesaCLUB.php
├── procesaENTRENADOR.php
├── procesaESTADIO.php
├── procesaTABLA.php
│
└── img/
    ├── 76GameBanner.jpg
    ├── FIA-21.png
    ├── fifa.jpeg
    ├── estadio.jpg
    ├── liga.jpg
    ├── champions.jpg
    └── premier.jpg
```

The `procesa*.php` files receive requests from the website and perform the corresponding operations on the MySQL database.

The `.js` files are mainly responsible for handling the interaction between the website and the PHP files and displaying the results in tables.

---

## 10. Troubleshooting

### The website does not load

Make sure **Apache is running** in XAMPP and that you are accessing the website through `localhost`.

### A MySQL-related error appears

Make sure **MySQL is running** and that the `Fifa` database exists.

You can also check the database through phpMyAdmin:

```
http://localhost/phpmyadmin/
```

### The tables are empty

Make sure that `FIFAconInserc.sql` was imported correctly and that the `Fifa` database contains the required tables and data.

### The styles or tables do not display correctly

Make sure you have an Internet connection, since Bootstrap, jQuery, Popper.js and DataTables are loaded from external servers.

### Opening the HTML file directly does not work

This is expected. The project uses PHP and MySQL.

You need to start Apache and open the website through an address such as:

```
http://localhost/Fifa/Web%20FIFA%2021.html
```

---

## 11. Running the project after the initial setup

Once the initial configuration has been completed, you only need to:

1. Open XAMPP.
2. Start **Apache**.
3. Start **MySQL**.
4. Open the website in your browser:

   http://localhost/Fifa/Web%20FIFA%2021.html

There is no need to import the database again every time you run the project.

---

## Note for GitHub

If you download this project from GitHub, keep in mind that GitHub only stores the project files. **XAMPP and MySQL are not included in the repository**, so anyone who wants to run the project on their own computer will need to install XAMPP and follow the setup instructions above.

It is also important to keep the project's folder structure, especially the `img` folder, since the HTML file uses relative paths to load the images.
