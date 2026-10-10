# Sistema de Gestión Escolar

Sistema de gestión escolar orientado a la administración de información académica de una institución educativa.

El proyecto utiliza **Microsoft SQL Server** como sistema gestor de base de datos para almacenar y organizar información relacionada con alumnos, académicos, aulas, carreras, ciudades, estados, países, estatus, grupos, materias y reinscripciones.

La base de datos permite centralizar la información de las diferentes entidades del sistema escolar y cuenta con tablas para almacenar los registros correspondientes a cada módulo.

## Módulos incluidos

### Alumnos

Permite almacenar y administrar la información de los alumnos.

Entre los datos manejados se encuentran:

* Nombre
* Apellidos
* Estatus
* Fecha y hora de creación

Tabla principal:

```text
Alumno
```

### Académicos

Permite almacenar la información de los profesores o académicos de la institución.

Los registros contienen información como:

* Nombre
* Apellidos
* Grado académico
* Fecha y hora de creación

Tabla principal:

```text
Academico
```

### Aulas

Permite almacenar información de las aulas disponibles dentro de la institución.

Se manejan datos como:

* Edificio
* Número de aula
* Piso
* Capacidad máxima
* Fecha y hora de creación

Tabla principal:

```text
Aula
```

### Carreras

Permite registrar y organizar las carreras académicas.

Los registros incluyen:

* Nombre de la carrera
* Siglas de la carrera
* Fecha y hora de creación

Tabla principal:

```text
Carrera
```

### Ubicación

La base de datos incluye tablas para almacenar información geográfica relacionada con la ubicación de las instituciones.

Se contemplan las siguientes entidades:

* Países
* Estados
* Ciudades

Tablas principales:

```text
Pais
Estado
Ciudad
```

Las tablas de ubicación incluyen campos para identificar sus registros y relacionar ciudades con estados, así como estados con países.

### Estatus

Permite almacenar información de los diferentes estatus utilizados dentro del sistema escolar.

Los registros incluyen:

* Clave de estatus
* Nombre del estatus
* Usuario
* Fecha y hora de creación

Tabla principal:

```text
Estatus
```

### Materias

Permite almacenar información de las materias disponibles dentro del sistema académico.

La tabla contempla campos para registrar:

* Nombre de la materia
* Créditos
* Fecha y hora de creación

Tabla principal:

```text
Materia
```

### Grupos

Permite almacenar información de los grupos académicos y los datos asociados a su organización.

Los campos contemplados incluyen:

* Alumno
* Maestro
* Aula
* Horario
* Carrera

Tabla principal:

```text
Grupo
```

### Reinscripciones

Permite almacenar los registros de reinscripción de los alumnos dentro del sistema escolar.

Esta entidad forma parte de la estructura de la base de datos y se utiliza para mantener la información correspondiente a las reinscripciones.

Tabla principal:

```text
Reinscripcion
```

## Base de datos

El proyecto utiliza **Microsoft SQL Server** como motor de base de datos.

El nombre de la base de datos es:

```text
BDEscolar
```

El script de creación de la base de datos se encuentra en el archivo:

```text
BDESCOLAR.sql
```

Este archivo contiene instrucciones SQL para crear la base de datos, definir las tablas y cargar datos iniciales.

La base de datos está diseñada para organizar la información escolar mediante diferentes entidades, cada una con sus propios campos y claves primarias.

## Tablas

La base de datos contiene las siguientes tablas principales:

| Tabla | Descripción |
|---|---|
| `Academico` | Información de los profesores o académicos |
| `Alumno` | Información de los alumnos |
| `Aula` | Información de las aulas |
| `Carrera` | Carreras académicas |
| `Ciudad` | Información de las ciudades |
| `Estado` | Estados o entidades federativas |
| `Estatus` | Catálogo de estatus |
| `Grupo` | Información de los grupos académicos |
| `Materia` | Información de las materias |
| `Pais` | Información de los países |
| `Reinscripcion` | Registros de reinscripción |

Las tablas utilizan claves primarias para identificar sus registros. La estructura también contempla campos de identificación que permiten asociar información de las distintas entidades escolares.

## Relaciones entre entidades

La estructura de la base de datos contempla información que permite asociar las entidades del sistema.

Entre los datos relacionados se encuentran:

* La información geográfica de países, estados y ciudades.
* Los alumnos y los grupos académicos.
* Los académicos y los grupos.
* Las aulas, los horarios y las carreras.
* Los registros de reinscripción.

Estas asociaciones permiten organizar la información de la institución en diferentes tablas, evitando concentrar todos los datos en una sola estructura.

## Vistas SQL

El archivo `BDESCOLAR.sql` proporcionado no contiene definiciones de vistas SQL.

Por lo tanto, no se documentan nombres de vistas específicos hasta verificar si existen en otro archivo o proyecto de la solución.

## Procedimientos almacenados

El archivo `BDESCOLAR.sql` proporcionado tampoco contiene definiciones de procedimientos almacenados.

Las operaciones de creación, actualización y eliminación de registros deberán documentarse de acuerdo con la implementación real del proyecto de aplicación o con los scripts SQL adicionales, si existen.

## Tecnologías utilizadas

* **Microsoft SQL Server**
* **SQL Server Management Studio**

La tecnología y la versión del framework utilizados por la aplicación de escritorio deben confirmarse mediante los archivos del proyecto de software.

## Instalación y ejecución

### 1. Requisitos

Para crear y administrar la base de datos se necesita:

* **Windows**
* **Microsoft SQL Server**
* **SQL Server Management Studio**

Si se utiliza una aplicación de escritorio asociada a esta base de datos, también será necesario instalar las herramientas y dependencias correspondientes a dicho proyecto.

### 2. Obtener los archivos del proyecto

Descargar o clonar el repositorio desde GitHub.

Si el repositorio se encuentra disponible en la siguiente dirección:

```bash
git clone https://github.com/JulioJuSalido/Sistema-Gestion-Escolar.git
```

Entrar al directorio del proyecto:

```bash
cd Sistema-Gestion-Escolar
```

### 3. Crear la base de datos

Abrir el archivo:

```text
BDESCOLAR.sql
```

desde **SQL Server Management Studio**.

Conectarse a la instancia de SQL Server correspondiente y ejecutar el script.

El script crea la base de datos:

```text
BDEscolar
```

También contiene la definición de las tablas y los datos iniciales incluidos en el archivo.

**Nota:** el script utiliza una configuración de archivos de base de datos asociada a una instalación específica de SQL Server. Si la instancia o las rutas locales son diferentes, puede ser necesario ajustar las rutas de los archivos de datos y del registro antes de ejecutarlo.

### 4. Configurar la conexión

Si la solución incluye una aplicación que se conecta a la base de datos, será necesario configurar la cadena de conexión para utilizar la instancia de SQL Server instalada en el equipo.

Por ejemplo, para una instancia local llamada `SQLEXPRESS`:

```csharp
Server=localhost\\SQLEXPRESS;
Database=BDEscolar;
Integrated Security=True;
TrustServerCertificate=True;
```

La cadena debe adaptarse al mecanismo de conexión utilizado por la aplicación. Si el proyecto utiliza autenticación de SQL Server, deberán configurarse las credenciales correspondientes.

### 5. Ejecutar el proyecto

Si el repositorio incluye una solución de Visual Studio, abrir el archivo `.sln` correspondiente y verificar que las dependencias estén instaladas.

Después, compilar y ejecutar la aplicación de acuerdo con la configuración del proyecto.

El archivo de solución, el formulario principal y el punto de entrada deberán identificarse en los archivos reales de la aplicación.

### Imagen
<img width="612" height="377" alt="image" src="https://github.com/user-attachments/assets/27c36c67-ba30-4d37-9f77-f0c7e39dbf9f" />
