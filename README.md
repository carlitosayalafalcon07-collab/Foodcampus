Descripción

FoodCampus es una aplicación de consola desarrollada en .NET 10 con C# 14 que simula un sistema de pedidos de comida dentro de un entorno universitario.
El sistema permite registrar restaurantes, administrar sus menús y realizar pedidos seleccionando platillos disponibles.

El proyecto fue desarrollado utilizando Clean Architecture para mantener una separación clara de responsabilidades entre las diferentes capas del sistema.

Además, el desarrollo del proyecto se apoyó en ingeniería de prompts con Inteligencia Artificial, donde cada componente del sistema fue generado mediante prompts estructurados.

Características principales

El sistema permite:

Registrar restaurantes

Registrar el menú de cada restaurante

Consultar restaurantes disponibles

Realizar pedidos seleccionando platillos del menú

Consultar pedidos realizados por usuario

Manejar errores de entrada en consola

Validar datos del dominio

Arquitectura del proyecto

El proyecto sigue el patrón Clean Architecture, dividiendo el sistema en cuatro capas principales

Contiene:

Entidades del sistema

Reglas de negocio

Extension members

No depende de ninguna otra capa.

Application

Contiene:

Casos de uso

DTOs

Interfaces de repositorios

Define la lógica de aplicación sin depender de infraestructura.

Infrastructure

Contiene:

Implementaciones de repositorios

Acceso a base de datos con Dapper

Modelos de base de datos

Mappers entre dominio y base de datos

ConsoleUI

Contiene:

Menú interactivo en consola

Flujo de interacción con el usuario

Configuración del sistema en Program.cs

Tecnologías utilizadas

.NET 10

C# 14

SQL Server

Dapper

Dependency Injection

Clean Architecture

Microsoft.Extensions.DependencyInjection

Base de datos

El sistema utiliza SQL Server alojado en Somee.

Tablas principales:

Restaurant

Order

OrderDetail

Relaciones:

Restaurant
    |
    | 1..N
    |
Order
    |
    | 1..N
    |
OrderDetail
Funcionalidades del menú de consola

Al iniciar la aplicación se muestra el siguiente menú:

1 Registrar restaurante
2 Consultar restaurantes
3 Realizar pedido
4 Consultar pedidos por usuario
5 Salir
Registro de restaurante

Permite capturar:

Nombre del restaurante

Especialidad

Horario de apertura

Horario de cierre

Posteriormente se abre un submenú para registrar platillos.

Registro de menú del restaurante

Opciones:

1 Agregar platillo
2 Ver platillos agregados
3 Finalizar registro

Cada platillo incluye:

Nombre

Precio

Descripción opcional

Realizar pedido

El sistema permite:

Seleccionar restaurante

Mostrar menú disponible

Elegir platillos

Indicar cantidad

Confirmar pedido

El sistema muestra un resumen final del pedido.

Ingeniería de Prompts

El desarrollo del sistema se realizó mediante prompts estructurados para IA, almacenados en la carpeta:

/prompts

Lista de prompts utilizados:

01_architecture_prompt.md
02_database_design_prompt.md
03_sql_tables_prompt.md
04_dummy_data_prompt.md
05_domain_entities_prompt.md
06_domain_extensions_prompt.md
07_dapper_models_prompt.md
08_mappers_prompt.md
09_repository_interfaces_prompt.md
10_repository_implementation_prompt.md
11_use_cases_prompt.md
12_console_menu_prompt.md
13_register_restaurant_menu_prompt.md
14_order_menu_selection_prompt.md
15_program_bootstrap_prompt.md

Cada prompt genera una parte específica del sistema sin romper la arquitectura.

Ejecución del proyecto
1 Clonar el repositorio
git clone https://github.com/usuario/foodcampus.git
2 Configurar la conexión a base de datos

Modificar la cadena de conexión en Program.cs:

Server=tu_servidor.somee.com;
Database=FoodCampusDB;
User Id=tu_usuario;
Password=tu_password;
3 Ejecutar la aplicación
dotnet run
Validaciones implementadas

El sistema incluye:

Validación de entradas numéricas con TryParse

Manejo de excepciones

Mensajes de error en consola

Validaciones en entidades de dominio

Ejemplos:

Precio de platillo mayor a 0

Cantidad mayor a 0

Costo de envío no negativo

Principios aplicados

El proyecto aplica los siguientes principios de diseño:

SOLID

Clean Architecture

Separación de responsabilidades

Inyección de dependencias

Programación asíncrona

Autor

Proyecto desarrollado como examen final de Desarrollo de Software Multiplataforma.

Autores:
Carlos Ayala,Jose Cardenas
