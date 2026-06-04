# 🧠 Bot de Gestión de Vacaciones (Python + Excel)

## 👨‍💻 Autores
**Padin Elisa**  
**Gatica Emmanuel David**  

Proyecto académico – Universidad Tecnológica Nacional (UTN)  
Integrador de Organización Empresarial – 2026  

## 📌 Descripción

Este proyecto consiste en el desarrollo de un chatbot por consola en Python para la gestión de solicitudes de vacaciones dentro de una organización.

El sistema permite a un empleado identificarse mediante su legajo, consultar sus días disponibles, solicitar un período de vacaciones y registrar la solicitud en un archivo Excel. Además, simula la intervención de un supervisor que puede aprobar o rechazar la solicitud.

Si la solicitud es aprobada, el sistema actualiza automáticamente los días usados y los días disponibles del empleado. Si no hay saldo suficiente, la solicitud es rechazada automáticamente por el sistema.

---

## 🎯 Objetivo

Automatizar el proceso de solicitud de vacaciones mediante una aplicación sencilla, utilizando una base de datos simulada en Excel y aplicando reglas de negocio relacionadas con:

- Validación de datos
- Verificación de saldo disponible
- Registro histórico de solicitudes
- Aprobación o rechazo por parte del supervisor

---

## ⚙️ Funcionalidades principales

- Lectura de empleados desde un archivo Excel
- Validación del legajo ingresado
- Consulta de días disponibles
- Solicitud de vacaciones con fecha de inicio y fin
- Validación de fechas ingresadas
- Cálculo automático de días solicitados
- Rechazo automático por saldo insuficiente
- Registro de solicitudes en el historial
- Aprobación o rechazo manual por parte del supervisor
- Actualización del saldo del empleado al aprobarse la solicitud
- Manejo de errores al abrir o guardar el archivo Excel

---

## 🧠 Lógica general del sistema

El flujo implementado en el chatbot es el siguiente:

1. El usuario ingresa su legajo.
2. El sistema verifica si el empleado existe.
3. Se informa el saldo de días disponibles.
4. El usuario ingresa fecha de inicio y fecha de fin.
5. El sistema valida el formato y coherencia de las fechas.
6. Se calcula automáticamente la cantidad de días solicitados.
7. Si no hay saldo suficiente, la solicitud se rechaza automáticamente.
8. Si hay saldo, la solicitud se registra como pendiente.
9. El supervisor aprueba o rechaza la solicitud.
10. Si se aprueba, el sistema descuenta los días correspondientes.
11. El resultado final se guarda en el historial y se comunica al usuario.

---

## 🗂️ Estructura del archivo Excel

El sistema utiliza un archivo llamado:

`BBDD_empleados.xlsx`

Este archivo debe contener dos hojas:

### 1. `Empleados_vacaciones`

Contiene la información de los empleados y su saldo de vacaciones.

Campos utilizados en el código:

- Columna 1: `ID_Empleado` / Legajo
- Columna 2: `Nombre`
- Columna 3: `Apellido`
- Columna 6: `Dias_Usados`
- Columna 7: `Dias_Disponibles`

### 2. `Historico_vacaciones`

Contiene el registro de todas las solicitudes realizadas.

Campos utilizados:

- `ID_Solicitud`
- `ID_Empleado`
- `Fecha_Solicitud`
- `Fecha_Inicio`
- `Fecha_Fin`
- `Dias_Solicitados`
- `Estado`
- `Aprobado_Por`
- `Comentarios`

---

## 🔗 Reglas de negocio implementadas

- El legajo debe existir en la base de datos.
- El legajo debe ser numérico entero.
- La fecha de inicio no puede ser anterior al día actual.
- La fecha de fin debe ser igual o posterior a la fecha de inicio.
- Los días solicitados se calculan automáticamente a partir del rango de fechas.
- Si los días solicitados superan los días disponibles, la solicitud se rechaza automáticamente.
- Si hay disponibilidad, la solicitud pasa al supervisor.
- El supervisor puede aprobar o rechazar la solicitud.
- Si la solicitud es aprobada, se actualizan los días usados y los días disponibles del empleado.
- Toda solicitud queda registrada en el historial.

---

## 💻 Tecnologías utilizadas

- **Python**
- **openpyxl**
- **datetime**
- **Archivo Excel (.xlsx)** como base de datos simulada

---

## ▶️ Ejecución del proyecto

### Requisitos previos

- Tener Python instalado
- Instalar la biblioteca `openpyxl`

```bash
pip install openpyxl

