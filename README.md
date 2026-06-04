# 🧠 Bot de Gestión de Vacaciones (Python + Excel)

## 👨‍💻 Autores
**Padin Elisa**  
**Gatica Emmanuel David**  

Proyecto académico – Universidad Tecnológica Nacional (UTN)  
Integrador de Organización Empresarial – 2026  

---

## 📋 Descripción
Este proyecto implementa un **bot de gestión de vacaciones** en Python que simula un proceso **BPMN 2.0** entre tres actores: **empleado**, **bot** y **supervisor**.  
El sistema utiliza un archivo Excel (`BBDD_empleados.xlsx`) como base de datos para validar solicitudes y registrar el historial de vacaciones.

---

## ⚙️ Flujo del proceso
1. **Empleado**
   - Ingresa su legajo.
   - Solicita fechas de inicio y fin de vacaciones.

2. **Bot**
   - Verifica el legajo en la hoja `Empleados_vacaciones`.
   - Calcula los días solicitados.
   - Valida las fechas (formato, año y que no sean anteriores a hoy).
   - Controla el saldo de días disponibles.
   - Si el supervisor está de vacaciones, aprueba o rechaza automáticamente.

3. **Supervisor**
   - Recibe solicitudes pendientes.
   - Decide aprobar o rechazar.
   - Si rechaza, debe ingresar el motivo.

4. **Registro histórico**
   - Todas las solicitudes se guardan en la hoja `Historico_vacaciones` con su estado, responsable y comentario.

---

## 📂 Estructura del proyecto

├── import os.txt        # Script principal del bot
├── BBDD_empleados.xlsx  # Base de datos de empleados y vacaciones
└── README.md            # Documentación del proyecto


---

## 🧠 Requisitos
- Python 3.10 o superior  
- Librería necesaria:
```bash
pip install openpyxl
```

🚀 Ejecución
Ejecutar el script desde la terminal:
```bash
python import\ os.txt
```
## 🧩 Durante la ejecución

- El bot solicitará legajo y fechas.  
- Validará la información.  
- Guardará los resultados en el archivo Excel.

## 📊 Estructura del archivo Excel

Hoja Empleados_vacaciones
| Columna | Descripción |
| --- | --- |
| Legajo | Identificador del empleado |
| Nombre | Nombre del empleado |
| Apellido | Apellido del empleado |
| Días totales | Días de vacaciones asignados |
| Días usados | Días ya tomados |
| Días disponibles | Días restantes |

Hoja Historico_vacaciones

| Columna | Descripción |
| --- | --- |
| ID | Identificador de solicitud |
| Legajo | Empleado solicitante |
| Fecha solicitud | Fecha en que se registró |
| Fecha inicio | Inicio de vacaciones |
| Fecha fin | Fin de vacaciones |
| Días solicitados | Cantidad de días |
| Estado | Pendiente, Aprobada, Rechazada |
| Responsable | Supervisor o Sistema |
| Comentario | Motivo o detalle |

## 🧰 Funcionalidades destacadas

- Validación de fechas y formato.  
- Control de saldo de vacaciones.  
- Aprobación automática si el supervisor está de vacaciones.  
- Registro histórico de todas las solicitudes.  
- Mensajes interactivos simulando diálogo entre empleado, bot y supervisor.

## 🍀 Ejemplo de interacción

```bash
Ingrese su legajo: 3  
Bot: Bienvenido/a Juan Pérez.  
Bot: Usted dispone de 12 días.  

=== SOLICITUD DE VACACIONES ===  
Ingrese fecha de inicio (DD/MM/AAAA): 15/09/2026  
Ingrese fecha de fin (DD/MM/AAAA): 20/09/2026  

Bot: Días calculados automáticamente: 6  
Bot: Validando información...  
Bot: Atención. El supervisor se encuentra de vacaciones.  
Bot: Solicitud aprobada automáticamente.  
Bot: Nuevo saldo disponible: 6 días.
```

