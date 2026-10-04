# 🎓 Sistema de Gestión Escolar

Sistema de escritorio desarrollado en **C# y Windows Forms** para la gestión de información académica y administrativa de una institución educativa.

El proyecto utiliza **SQL Server** como sistema gestor de base de datos y permite administrar diferentes entidades relacionadas con el funcionamiento académico, incluyendo alumnos, académicos, aulas, carreras, materias, grupos y reinscripciones.

La aplicación se comunica con la base de datos mediante `Microsoft.Data.SqlClient` y utiliza **procedimientos almacenados y vistas SQL** para realizar las operaciones de consulta, creación, actualización y eliminación de información.

## 📋 Módulos incluidos

Actualmente el sistema contiene diferentes módulos para administrar la información escolar:

### 👨‍🎓 Alumnos

Permite registrar y administrar la información de los alumnos.

Entre los datos manejados se encuentran:

* Nombre
* Apellidos
* Estatus
* Fecha y hora de creación

Archivo principal:

```text
Alumno.cs
```

### 👨‍🏫 Académicos

Permite administrar la información de los profesores o académicos.

Los registros contienen información como:

* Nombre
* Apellidos
* Grado académico
* Fecha y hora de creación

Archivo principal:

```text
Academico.cs
```

### 🏫 Aulas

Permite administrar las aulas disponibles dentro de la institución.

Se manejan datos como:

* Edificio
* Aula
* Piso
* Capacidad máxima
* Fecha y hora de creación

Archivo principal:

```text
Aula.cs
```

### 🎓 Carreras

Permite registrar y administrar las diferentes carreras académicas.

Los registros incluyen:

* Nombre de la carrera
* Siglas
* Fecha y hora de creación

Archivo principal:

```text
Carrera.cs
```

### 🌎 Ubicación

El sistema cuenta con módulos para administrar información geográfica relacionada con las instituciones:

* Países
* Estados
* Ciudades

Archivos principales:

```text
Pais.cs
EstadosE.cs
Ciudad.cs
```

### 📚 Materias

Permite administrar las materias disponibles dentro del sistema académico.

Se manejan:

* Nombre de la materia
* Créditos
* Fecha y hora de creación

Archivo principal:

```text
Materia.cs
```

### 👥 Grupos

Permite relacionar diferentes elementos del sistema académico para crear grupos.

Un grupo puede relacionar:

* Alumno
* Académico
* Aula
* Carrera
* Horario

Archivo principal:

```text
Grupo.cs
```

### 📝 Reinscripciones

Permite registrar la reinscripción de alumnos a grupos y almacenar su calificación.

Los registros incluyen:

* Alumno
* Grupo
* Calificación
* Fecha y hora de creación

Archivo principal:

```text
Reinscripcion.cs
```

## 🗄️ Base de datos

El sistema utiliza **Microsoft SQL Server** como motor de base de datos.

La base de datos utilizada por el proyecto se denomina:

```text
GruposBD
```

El script de la base de datos se encuentra en:

```text
BDEscolar.sql
```

Este archivo contiene la estructura necesaria para crear la base de datos, tablas, vistas, procedimientos almacenados y datos iniciales.

## 📊 Tablas

La base de datos contiene las siguientes tablas principales:

| Tabla          | Descripción                                 |
| -------------- | ------------------------------------------- |
| `Alumnos`      | Información de los alumnos                  |
| `Academico`    | Información de profesores o académicos      |
| `Aula`         | Información de las aulas                    |
| `Carrera`      | Carreras académicas                         |
| `Ciudad`       | Ciudades                                    |
| `Estado`       | Estados o entidades federativas             |
| `Estatus`      | Catálogo de estatus                         |
| `Grupo`        | Grupos académicos                           |
| `Materia`      | Materias y créditos                         |
| `Pais`         | Países                                      |
| `Reincripcion` | Registros de reinscripción y calificaciones |

Las tablas utilizan claves primarias y relaciones mediante claves foráneas para mantener la integridad de la información.

## 👁️ Vistas SQL

El proyecto utiliza vistas para facilitar la consulta de información desde la aplicación.

Entre las vistas disponibles se encuentran:

```text
viewAlumnos
viewAcademico
viewAula
viewCarrera
viewCiudad
viewEstado
viewEstatus
viewGrupo
viewMateria
viewPais
viewReinscripcion
viewDireccion
viewReinscripcionesCompleto
viewGrupoMaestro
viewAlumnosCarreras
viewGrupoCompleto
```

Estas vistas permiten obtener información individual de las diferentes entidades y también generar consultas que combinan información de varias tablas.

Por ejemplo:

```text
viewGrupoCompleto
```

permite consultar información relacionada con grupos, académicos, aulas, carreras y alumnos.

De manera similar:

```text
viewReinscripcionesCompleto
```

combina información de reinscripciones con alumnos, grupos, académicos, carreras y aulas.

## ⚙️ Procedimientos almacenados

Las operaciones de modificación de datos se realizan mediante **procedimientos almacenados de SQL Server**.

El proyecto incluye procedimientos para:

### Crear

```text
sp_CrearAcademicos
sp_CrearAlumnos
sp_CrearAulas
sp_CrearCarreras
sp_CrearCiudades
sp_CrearEstados
sp_CrearGrupo
sp_CrearMaterias
sp_CrearPaises
sp_CrearReinscripcion
```

### Actualizar

```text
sp_ActualizarAcademicos
sp_ActualizarAlumnos
sp_ActualizarAulas
sp_ActualizarCarreras
sp_ActualizarCiudades
sp_ActualizarEstados
sp_ActualizarGrupo
sp_ActualizarMaterias
sp_ActualizarPaises
sp_AcualizarReinscripcion
```

### Eliminar

```text
sp_EliminarAcademico
sp_EliminarAlumno
sp_EliminarAula
sp_EliminarCarrera
sp_EliminarCiudad
sp_EliminarEstado
sp_EliminarGrupo
sp_EliminarMateria
sp_EliminarPais
sp_EliminarReinscripcion
```

Esto permite separar parte de la lógica de acceso y modificación de datos entre la aplicación y el servidor de base de datos.

## ✨ Características

* 🎓 Gestión de información escolar.
* 👨‍🎓 Administración de alumnos.
* 👨‍🏫 Administración de académicos.
* 🏫 Administración de aulas.
* 📚 Administración de materias.
* 🎓 Administración de carreras.
* 👥 Administración de grupos.
* 📝 Registro de reinscripciones.
* 📊 Consulta de información mediante `DataGridView`.
* ✏️ Edición de registros.
* ➕ Creación de registros.
* 🗑️ Eliminación de registros.
* 🔗 Relaciones entre diferentes entidades académicas.
* 🗄️ Integración con SQL Server.
* ⚙️ Uso de procedimientos almacenados.
* 👁️ Uso de vistas SQL para consultas.
* 🖥️ Interfaz gráfica desarrollada con Windows Forms.

## 🛠️ Tecnologías utilizadas

* **C#**
* **.NET 9**
* **Windows Forms**
* **Microsoft SQL Server**
* **Microsoft.Data.SqlClient**
* **Visual Studio**
* **SQL Server Management Studio**

## 🔌 Conexión con la base de datos

La aplicación utiliza una cadena de conexión para comunicarse con SQL Server.

La clase encargada de centralizar parte de esta comunicación es:

```text
ConexionesBD.cs
```

Esta clase contiene consultas utilizadas para cargar información mediante las vistas SQL, por ejemplo:

```csharp
SELECT * FROM viewAlumnos
```

```csharp
SELECT * FROM viewAcademico
```

```csharp
SELECT * FROM viewGrupoCompleto
```

```csharp
SELECT * FROM viewReinscripcionesCompleto
```

> ⚠️ La cadena de conexión incluida actualmente en el código está configurada para una instancia específica de SQL Server. Para ejecutar el proyecto en otro equipo es necesario modificarla de acuerdo con la configuración local.

## 🚀 Instalación y ejecución

### 1. Requisitos

Para ejecutar el proyecto se necesita:

* **Windows**
* **Visual Studio**
* **.NET 9 SDK**
* **SQL Server**
* **SQL Server Management Studio** (recomendado)

### 2. Clonar el repositorio

```bash
git clone https://github.com/JulioJuSalido/Sistema-Gestion-Escolar.git
```

Entrar al directorio:

```bash
cd Sistema-Gestion-Escolar
```

### 3. Crear la base de datos

Abrir el archivo:

```text
BDEscolar.sql
```

desde **SQL Server Management Studio** y ejecutar el script.

El script crea la base de datos:

```text
GruposBD
```

junto con sus tablas, vistas, procedimientos almacenados y registros iniciales.

### 4. Configurar la conexión

Abrir:

```text
SistemaEscolarBD/ConexionesBD.cs
```

y modificar la cadena de conexión para utilizar la instancia de SQL Server disponible en el equipo.

Por ejemplo:

```csharp
public string connexion =
    "Server=SERVIDOR\\SQLEXPRESS;" +
    "Database=GruposBD;" +
    "Integrated Security=True;" +
    "TrustServerCertificate=True";
```

### 5. Ejecutar el proyecto

Abrir la solución:

```text
SistemaEscolarBD/SistemaEscolarBD.sln
```

desde Visual Studio.

Después compilar y ejecutar el proyecto.

El punto de entrada de la aplicación se encuentra en:

```text
Program.cs
```

y ejecuta el formulario principal del sistema.
