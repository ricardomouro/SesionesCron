# Descripción del MVP - Sesiones Control

## Descripción General

Sesiones Control es una aplicación PWA (Progressive Web App) diseñada para profesionales que gestionan consultas y sesiones. Simplifica el registro de pacientes, el seguimiento financiero y la organización de la agenda, incluyendo el control de la facturación. Ideal para psicólogos, terapeutas, consultores y otros profesionales que trabajan por sesiones.

## Funcionalidades Principales

### A. Gestión de Pacientes

*   **Descripción:** Permite registrar y gestionar la información de los pacientes.
*   **Requisitos:**
    *   Listado de Pacientes (con opción de crear nuevo paciente)
    *   Crear Nuevo Paciente:
        *   Nombre: Campo de texto (obligatorio, validación de longitud mínima)
        *   Teléfono: Campo de texto (validación de formato, opcional)
        *   Precio Acordado por Sesión: Campo numérico (obligatorio, validación de valor mínimo)
        *   Moneda: Selector desplegable (Pesos Argentinos / Reales, valor por defecto configurable)
        *   Notas: Área de texto (opcional, longitud máxima)
    *   Editar Paciente: Mismos campos que "Crear Nuevo Paciente" con los datos precargados.
    *   Eliminar Paciente: Confirmación antes de eliminar.

### B. Registro de Consultas

*   **Descripción:** Permite registrar y gestionar las consultas de los pacientes.
*   **Requisitos:**
    *   Agenda/Calendario (vista semanal o mensual) con opción de agregar nueva consulta.
    *   Agregar Nueva Consulta:
        *   Paciente: Selector desplegable (obligatorio, lista de pacientes registrados).
        *   Fecha y Hora: Selectores de fecha y hora (obligatorios).
        *   Estado de la Consulta: Selector desplegable (Programada, Cancelada/Falta, Realizada, valor por defecto "Programada").
        *   Estado de Pago: Checkbox (Pagado, valor por defecto "No").
        *   Estado de Facturación: Checkbox (Facturado, valor por defecto "No").
    *   Editar Consulta: Mismos campos que "Agregar Nueva Consulta" con los datos precargados.
    *   Eliminar Consulta: Confirmación antes de eliminar.

### C. Gestión Financiera

*   **Descripción:** Permite visualizar los pagos pendientes y realizados por paciente.
*   **Requisitos:**
    *   Listado de Pagos por Paciente (se accede desde la pantalla de Gestión de Pacientes)
        *   Muestra todas las consultas del paciente seleccionado.
        *   Muestra para cada consulta: Fecha, Estado de la Consulta, Precio Acordado, Estado de Pago, Estado de Facturación.
        *   Total Pagado por Paciente (suma de los precios acordados de las consultas marcadas como "Pagado").
        *   Total Pendiente por Paciente (suma de los precios acordados de las consultas NO marcadas como "Pagado").

### D. Informes Básicos

*   **Descripción:** Permite generar un informe mensual con los ingresos y pagos pendientes.
*   **Requisitos:**
    *   Informe Mensual
        *   Selector de Mes/Año: Selectores desplegables (obligatorios).
        *   Tabla con:
            *   Paciente: Nombre del paciente.
            *   Valor Recibido: Suma de los precios acordados de las consultas marcadas como "Pagado" en el mes seleccionado.
            *   Valor Pendiente: Suma de los precios acordados de las consultas NO marcadas como "Pagado" en el mes seleccionado.
        *   Total Recibido (General): Suma de todos los "Valor Recibido".
        *   Total Pendiente (General): Suma de todos los "Valor Pendiente".

### E. Autenticación

*   **Descripción:** Permite al profesional acceder a la aplicación de forma segura.
*   **Requisitos:**
    *   Pantalla de Login:
        *   Usuario: Campo de texto (obligatorio)
        *   Contraseña: Campo de texto (obligatorio, tipo "password")
        *   Botón "Iniciar Sesión"
    *   Manejo de la Sesión: Almacenar la información del usuario logueado (en este caso, solo el usuario único).
    *   Pantalla de Configuración (Opcional): Permitir al usuario cambiar su contraseña.

# Requisitos Técnicos

*   **Lenguaje de Programación:** C#
*   **Framework:** .NET Core con ASP.NET (Blazor)
*   **Base de Datos:** Azure Cosmos DB (API para NoSQL)
*   **IDE:** Visual Studio 2022
*   **Control de Versiones:** Git (GitHub)
*   **Plataforma de Despliegue:** Azure (App Service para la API, PWA)
*   **Tipo de Aplicación:** PWA (Progressive Web App)

# Plan de Actividades (Estimación de Tiempo)

*   **Sprint 1: Preparación del Entorno y Autenticación (1 semana)**
    *   Configuración del proyecto .NET Core y Blazor.
    *   Configuración de Azure Cosmos DB.
    *   Implementación del sistema de login básico.
*   **Sprint 2: Gestión de Pacientes (2 semanas)**
    *   Desarrollo de la interfaz para el listado, creación, edición y eliminación de pacientes.
    *   Implementación de la lógica de negocio y el acceso a la base de datos para la gestión de pacientes.
*   **Sprint 3: Registro de Consultas (2 semanas)**
    *   Desarrollo de la interfaz para el registro de consultas (agenda, creación, edición, eliminación).
    *   Implementación de la lógica de negocio y el acceso a la base de datos para el registro de consultas.
*   **Sprint 4: Gestión Financiera (1 semana)**
    *   Desarrollo de la interfaz para la visualización de pagos por paciente.
    *   Implementación de la lógica para calcular los totales pagados y pendientes.
*   **Sprint 5: Informes Básicos (2 semanas)**
    *   Desarrollo de la interfaz para el informe mensual.
    *   Implementación de la lógica para generar el informe (cálculos y acceso a la base de datos).
*   **Sprint 6: Pruebas, Refinamiento y Despliegue (2 semanas)**
    *   Pruebas exhaustivas de todas las funcionalidades.
    *   Corrección de errores y refinamiento de la interfaz.
    *   Despliegue de la aplicación en Azure como PWA y la API.

# Modelo de Ejecución

*   **Roles:**
    *   **Product Manager/Usuario (Tú):** Definición de requisitos, validación, pruebas, implementación en el "mundo real".
    *   **Gerente de Proyectos/Arquitecto/Desarrollador/Sysop (Yo):** Diseño, desarrollo, configuración, despliegue, gestión técnica del proyecto.
*   **Proceso:**
    1.  Yo propongo una actividad específica del sprint con los pasos a seguir.
    2.  Tú realizas los pasos indicados y me informas cuando estén listos.
    3.  Realizamos iteraciones en caso de dudas o problemas.
*   **Herramientas:**
    *   Visual Studio 2022
    *   GitHub
