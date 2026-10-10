# Sistema de Gestión Escolar

Sistema de gestión escolar orientado a la organización y administración de información académica de una institución educativa.

El proyecto utiliza **Microsoft SQL Server** como sistema gestor de base de datos para almacenar información relacionada con alumnos, académicos, aulas, carreras, ciudades, estados, países, estatus, grupos, materias y reinscripciones.

La base de datos organiza la información en diferentes tablas, permitiendo mantener los registros de las entidades escolares y establecer relaciones entre los datos que forman parte del sistema.

## Módulos incluidos

### Alumnos

Almacena la información de los alumnos de la institución.

Los datos registrados incluyen:

* Nombre
* Apellidos
* Estatus
* Fecha y hora de creación

Tabla principal:

```text
Alumno
```

### Académicos

Contiene la información de los profesores o académicos de la institución.

Los registros incluyen:

* Nombre
* Apellidos
* Grado académico
* Fecha y hora de creación

Tabla principal:

```text
Academico
```

### Aulas

Almacena información de las aulas disponibles dentro de la institución.

Se contemplan los siguientes datos:

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

Permite organizar la información de las carreras académicas.

Los registros incluyen:

* Nombre de la carrera
* Siglas
* Fecha y hora de creación

Tabla principal:

```text
Carrera
```

### Ubicación

Organiza la información geográfica mediante entidades que permiten identificar la ubicación de las instituciones.

Incluye las siguientes tablas:

* Países
* Estados
* Ciudades

Tablas principales:

```text
Pais
Estado
Ciudad
```

Estas entidades permiten relacionar las ciudades con sus respectivos estados y los estados con sus países.

### Estatus

Contiene el catálogo de estatus utilizados en el sistema escolar.

Los datos registrados incluyen:

* Clave de estatus
* Nombre del estatus
* Usuario
* Fecha y hora de creación

Tabla principal:

```text
Estatus
```

### Materias

Almacena la información de las materias que forman parte del sistema académico.

Los datos contemplados incluyen:

* Nombre de la materia
* Créditos
* Fecha y hora de creación

Tabla principal:

```text
Materia
```

### Grupos

Organiza la información relacionada con los grupos académicos y los elementos asociados a su estructura.

Entre los datos relacionados se encuentran:

* Alumnos
* Académicos
* Aulas
* Horarios
* Carreras

Tabla principal:

```text
Grupo
```

### Reinscripciones

Contiene los registros correspondientes a las reinscripciones de los alumnos dentro del sistema escolar.

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

El script de creación se encuentra en el archivo:

```text
BDESCOLAR.sql
```

Este archivo contiene las instrucciones SQL para crear la base de datos, definir las tablas e insertar los datos iniciales incluidos en el script.

## Tablas

La base de datos contiene las siguientes tablas principales:

| Tabla | Descripción |
|---|---|
| `Academico` | Información de los profesores o académicos |
| `Alumno` | Información de los alumnos |
| `Aula` | Información de las aulas |
| `Carrera` | Información de las carreras académicas |
| `Ciudad` | Información de las ciudades |
| `Estado` | Información de los estados o entidades federativas |
| `Estatus` | Catálogo de estatus |
| `Grupo` | Información de los grupos académicos |
| `Materia` | Información de las materias |
| `Pais` | Información de los países |
| `Reinscripcion` | Registros de reinscripción |

Cada tabla almacena información específica de una entidad del sistema. Las claves primarias permiten identificar los registros y las relaciones entre las entidades ayudan a mantener organizada la información.

## Relaciones entre entidades

La estructura de la base de datos permite organizar información relacionada con las diferentes áreas del sistema escolar.

Entre las relaciones contempladas se encuentran:

* Países, estados y ciudades.
* Alumnos y grupos académicos.
* Académicos y grupos.
* Aulas, horarios y carreras.
* Registros de reinscripción.

Esta organización permite distribuir la información entre diferentes tablas y facilitar su administración.

## Tecnologías utilizadas

* **Microsoft SQL Server**
* **SQL Server Management Studio**

## Instalación y ejecución

### 1. Requisitos

Para crear y administrar la base de datos se necesita:

* **Windows**
* **Microsoft SQL Server**
* **SQL Server Management Studio**

### 2. Clonar el repositorio

Clonar el repositorio desde GitHub:

```bash
git clone https://github.com/JulioJuSalido/SistemadeGestion-Escolar.git
```

Entrar al directorio del proyecto:

```bash
cd SistemadeGestion-Escolar
```

### 3. Crear la base de datos

Abrir el archivo:

```text
BDESCOLAR.sql
```

desde **SQL Server Management Studio**.

Conectarse a la instancia de SQL Server correspondiente y ejecutar el script para crear la base de datos `BDEscolar`, sus tablas y los datos iniciales incluidos.

**Nota:** el script puede contener rutas de archivos de datos asociadas a una instalación específica de SQL Server. Si las rutas o la configuración del servidor son diferentes, será necesario ajustarlas antes de ejecutar el script.

### 4. Configurar la conexión

Si se utiliza una aplicación para conectarse a la base de datos, la cadena de conexión debe apuntar a la instancia de SQL Server donde se creó `BDEscolar`.

Por ejemplo, para una instancia local llamada `SQLEXPRESS`:

```csharp
string connectionString =
    "Server=localhost\\SQLEXPRESS;" +
    "Database=BDEscolar;" +
    "Integrated Security=True;" +
    "TrustServerCertificate=True;";
```

La configuración debe adaptarse a la instancia instalada y al método de autenticación utilizado.

### 5. Ejecutar el proyecto

Una vez creada la base de datos, se puede utilizar desde la aplicación que se conecte a ella, siempre que la cadena de conexión y los requisitos correspondientes estén configurados correctamente.

## Imagen

<img width="612" height="377" alt="image" src="https://github.com/user-attachments/assets/a3020a23-ce2b-4d88-83ed-12eb62bea1e2" />

