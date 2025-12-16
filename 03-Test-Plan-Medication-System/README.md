# Plan de Pruebas de Software - Sistema de Gestión de Medicamentos

> **Proyecto académico de planificación exhaustiva de testing para sistema crítico de salud**

## 📋 Descripción del Proyecto

Plan completo de **Software Testing** para un sistema de información de gestión de medicamentos en entorno hospitalario. Este documento establece estrategias, metodologías y criterios para asegurar la calidad de un sistema crítico que maneja trazabilidad completa del flujo de medicamentos.

**Sistema:** Gestión de Medicamentos (Pharmacy Management System)  
**Cliente:** Clínica de Salud  
**Empresa:** SoftSena  
**Curso:** SENA - Calidad del Software (RAP3)  
**Fecha:** Diciembre 2025

---

## 🏥 Descripción del Sistema

### Tipo de Aplicación
- **Plataforma:** Aplicación de escritorio (Desktop)
- **Arquitectura:** Cliente-Servidor
- **Base de Datos:** RDBMS (Relacional)
- **Usuarios:** Múltiples usuarios concurrentes
- **Criticidad:** **ALTA** (entorno médico - gestión de medicamentos)

### Funcionalidades Principales

1. **Registro de Medicamentos Entregados**
   - Documentación de dispensación
   - Paciente, médico, fecha/hora, cantidades
   - Actualización automática de inventario

2. **Registro de Prescripciones Médicas**
   - Captura de formulaciones
   - Dosis, frecuencia, duración de tratamiento
   - Trazabilidad médico-paciente

3. **Gestión de Compras**
   - Registro de adquisiciones a proveedores
   - Costos, cantidades, fechas de recepción
   - Integración con inventario

4. **Consulta de Inventario**
   - Estado en tiempo real por laboratorio
   - Niveles de stock y alertas
   - Historial de movimientos

5. **Generación de Reportes**
   - Reportes diarios, semanales, mensuales
   - Exportación (PDF, Excel)
   - Análisis para toma de decisiones

---

## 🏆 Reconocimiento del Instructor

<details>
<summary><b>📸 Ver feedback completo</b></summary>

> **"Mateo, tu evidencia es de un nivel alto de profesionalismo. La estructura, el rigor técnico y el nivel de detalle son impecables."**
> 
> — **Carlos Alberto Hernández Arcila**  
> Instructor SENA - Calidad del Software  
> Diciembre 2025

**Criterios evaluados:**
1. ✅ Evidencia del modelo según ciclo de vida - Excelente justificación
2. ✅ Determine alcance de la prueba - Nivel de detalle excepcional
3. ✅ Relacione tipos de prueba - Lista exhaustiva y bien categorizada
4. ✅ Analice estrategias de pruebas - Nivel muy alto
5. ✅ Exponga criterios de salida - Sección de recursos y cronograma con viabilidad operativa

</details>

---

## 🔄 Modelo de Ciclo de Vida: Incremental

### ¿Por Qué Modelo Incremental?

El modelo incremental fue seleccionado por sus ventajas específicas para este proyecto:

✅ **Entrega temprana de funcionalidad**
- La clínica puede usar módulos esenciales mientras se desarrollan otros

✅ **Retroalimentación continua del cliente**
- Validación de cada incremento antes de continuar

✅ **Gestión de riesgos mejorada**
- Identificación temprana de problemas arquitecturales

✅ **Flexibilidad ante cambios**
- Ajuste de requisitos basado en experiencia previa

✅ **Validación progresiva**
- Testing exhaustivo de cada incremento aislado

✅ **Reducción de impacto de errores**
- Defectos más fáciles de localizar en incrementos pequeños

### Incrementos Planificados

```
┌─────────────────────────────────────────────────────────────┐
│ Incremento 1: Inventario Base                               │
│ • Registro de medicamentos                                  │
│ • Consultas de inventario                                   │
│ • CRUD de laboratorios                                      │
└─────────────────────────────────────────────────────────────┘
         ↓
┌─────────────────────────────────────────────────────────────┐
│ Incremento 2: Compras y Proveedores                         │
│ • Gestión de proveedores                                    │
│ • Registro de compras                                       │
│ • Actualización automática de inventario                    │
└─────────────────────────────────────────────────────────────┘
         ↓
┌─────────────────────────────────────────────────────────────┐
│ Incremento 3: Prescripciones y Dispensación                 │
│ • Registro médicos y pacientes                              │
│ • Gestión de prescripciones                                 │
│ • Dispensación de medicamentos                              │
│ • Trazabilidad completa                                     │
└─────────────────────────────────────────────────────────────┘
         ↓
┌─────────────────────────────────────────────────────────────┐
│ Incremento 4: Reportes y Análisis                           │
│ • Reportes configurables                                    │
│ • Exportación múltiples formatos                            │
│ • Analytics y dashboards                                    │
└─────────────────────────────────────────────────────────────┘
```

---

## 🧪 Tipos de Pruebas Aplicadas

### 1. Pruebas de Unidad

**Objetivo:** Verificar funcionamiento de módulos individuales

**Alcance:**
- Funciones de validación de datos
- Cálculos de dosis y cantidades
- Reglas de negocio aisladas

**Herramientas:** JUnit / NUnit (según tecnología)

**Responsable:** Desarrolladores

### 2. Pruebas de Integración

**Objetivo:** Validar interacción entre componentes

**Escenarios clave:**
- Frontend ↔ Backend
- Backend ↔ Base de Datos
- Módulo Compras ↔ Módulo Inventario
- Módulo Prescripciones ↔ Módulo Dispensación

**Técnica:** Big Bang + Bottom-Up

### 3. Pruebas de Sistema

**Objetivo:** Verificar el sistema completo integrado

**Pruebas funcionales:**
- Flujo completo de compra → actualización inventario
- Flujo prescripción médica → dispensación → reporte
- Generación de reportes con datos reales

**Pruebas no funcionales:**
- Performance (tiempo de respuesta < 2 seg)
- Usabilidad (facilidad de uso para personal médico)
- Seguridad (control de acceso por roles)

### 4. Pruebas de Validación

**Objetivo:** Confirmar cumplimiento de requisitos del cliente

**Métodos:**
- Revisión de trazabilidad Requisito → Caso de Prueba
- Validación de reportes contra especificaciones
- Verificación de reglas de negocio médicas

### 5. Pruebas de Aceptación (UAT)

**Objetivo:** Validación por usuarios finales

**Participantes:**
- Médicos
- Personal de farmacia
- Administradores

**Criterio de éxito:** 95% de casos de prueba aprobados

---

## 🎯 Estrategias de Pruebas

### Pruebas de Caja Blanca

**Aplicadas en:** Pruebas de Unidad

**Técnicas:**
- **Cobertura de Caminos:** Todos los flujos posibles
- **Cobertura de Decisiones:** Todas las ramas if/else
- **Cobertura de Condiciones:** Combinaciones booleanas
- **Análisis de Complejidad Ciclomática:** Identificar código complejo

**Meta de Cobertura:** ≥ 80% de líneas de código

### Pruebas de Caja Negra

**Aplicadas en:** Pruebas de Sistema y Aceptación

**Técnicas:**
- **Partición de Equivalencias:** Grupos de entradas similares
- **Análisis de Valores Límite:** Bordes de rangos válidos
- **Tablas de Decisión:** Combinaciones de condiciones
- **Pruebas de Transición de Estados:** Flujos de trabajo

**Ejemplo - Validación de Dosis:**
```
Particiones:
- Dosis válida (0.1 - 1000 mg)
- Dosis bajo límite (≤ 0 mg) → Error
- Dosis sobre límite (> 1000 mg) → Error

Valores Límite:
- 0, 0.1, 0.2 (límite inferior)
- 999.9, 1000, 1000.1 (límite superior)
```

---

## 📊 Criterios de Salida y Métricas

### Criterios de Salida del Testing

| Criterio | Umbral | Obligatorio |
|----------|--------|-------------|
| Cobertura de Código | ≥ 80% | ✅ Sí |
| Casos de Prueba Ejecutados | 100% | ✅ Sí |
| Casos de Prueba Aprobados | ≥ 95% | ✅ Sí |
| Defectos Críticos Abiertos | 0 | ✅ Sí |
| Defectos Altos Abiertos | ≤ 2 | ✅ Sí |
| Performance < 2 seg | 95% transacciones | ✅ Sí |

### Métricas de Calidad

**Densidad de Defectos:**
```
Defectos encontrados / KLOC ≤ 3
```

**Tasa de Detección de Defectos:**
```
(Defectos encontrados en testing / Total defectos) × 100 ≥ 90%
```

**Efectividad de las Pruebas:**
```
(Defectos detectados antes de producción / Total defectos) × 100
```

---

## 🛠️ Herramientas y Recursos

### Herramientas de Testing

| Categoría | Herramienta | Uso |
|-----------|-------------|-----|
| **Unit Testing** | JUnit / NUnit | Pruebas unitarias automatizadas |
| **Integration Testing** | Postman / SoapUI | Testing de APIs |
| **Functional Testing** | Selenium WebDriver | Automatización UI (si aplica) |
| **Performance Testing** | JMeter | Pruebas de carga |
| **Bug Tracking** | Jira | Gestión de defectos |
| **Coverage** | JaCoCo / SonarQube | Análisis de cobertura |

### Datos de Prueba

**Estrategia:**
- Base de datos de prueba con datos anonimizados
- Scripts SQL para restaurar estado inicial
- Generadores de datos aleatorios para volumen

**Consideraciones de Privacidad:**
- Datos de pacientes completamente ficticios
- Cumplimiento con regulaciones de datos médicos

---

## 📅 Plan de Ejecución

### Cronograma por Incremento

**Incremento 1 (Semanas 1-4):**
- Desarrollo: Semana 1-2
- Unit Testing: Semana 2-3
- Integration Testing: Semana 3
- System Testing: Semana 4

**Incremento 2 (Semanas 5-8):**
- Desarrollo: Semana 5-6
- Testing completo: Semana 7-8
- Regression Testing (Inc. 1): Semana 8

**Incremento 3 (Semanas 9-12):**
- Desarrollo: Semana 9-10
- Testing completo: Semana 11-12
- Regression Testing (Inc. 1+2): Semana 12

**Incremento 4 (Semanas 13-16):**
- Desarrollo: Semana 13-14
- Testing completo: Semana 15
- UAT Final: Semana 16

### Recursos Necesarios

**Equipo de Testing:**
- 1 QA Lead
- 2 QA Testers
- 1 Automation Engineer (medio tiempo)

**Infraestructura:**
- Servidor de pruebas dedicado
- Base de datos de prueba aislada
- Ambiente UAT separado

---

## 🎓 Conceptos Técnicos Aplicados

### Software Testing Life Cycle (STLC)

```
Requirement Analysis → Test Planning → Test Case Design
        ↓                                    ↓
    Test Environment Setup ← Test Execution → Defect Reporting
                                    ↓
                            Test Cycle Closure
```

### Niveles de Testing

```
        ┌─────────────────────┐
        │ Acceptance Testing  │ ← UAT
        ├─────────────────────┤
        │  System Testing     │ ← QA Team
        ├─────────────────────┤
        │ Integration Testing │ ← Developers + QA
        ├─────────────────────┤
        │   Unit Testing      │ ← Developers
        └─────────────────────┘
```

---

## 💡 Aspectos Destacados del Plan

### 1. **Enfoque en Criticidad**
Sistema de salud requiere 0 defectos críticos en producción - plan refleja esta exigencia.

### 2. **Testing Incremental**
Cada incremento se prueba exhaustivamente antes de integración.

### 3. **Trazabilidad Completa**
Matriz Requisito → Caso de Prueba → Defecto → Solución.

### 4. **Consideraciones de Seguridad**
Control de acceso, auditoría de acciones, encriptación de datos sensibles.

### 5. **Automatización Estratégica**
Pruebas de regresión automatizadas para cada incremento previo.

---

## 📁 Recursos

- 📄 [Plan de Pruebas Completo (PDF)](./Plan_Pruebas_Mateo_Algarra.pdf)
- 🖼️ [Feedback del Instructor](./feedback-instructor.png)

---

## 🎯 Competencias Demostradas

- ✅ Planificación exhaustiva de estrategias de testing
- ✅ Selección de modelo de ciclo de vida apropiado
- ✅ Definición de niveles de prueba (Unit, Integration, System, UAT)
- ✅ Aplicación de técnicas de caja blanca y caja negra
- ✅ Establecimiento de criterios de salida medibles
- ✅ Gestión de riesgos en testing
- ✅ Planificación de recursos y cronogramas
- ✅ Consideraciones de seguridad y privacidad en sistemas de salud

---

## 📈 Aplicabilidad Práctica

Este conocimiento es directamente aplicable en:
- Proyectos críticos de salud, finanzas o gobierno
- Establecimiento de procesos de QA desde cero
- Planificación de testing para desarrollo incremental/ágil
- Definición de estrategias de testing multi-nivel
- Gestión de proyectos con alta exigencia de calidad

---

<div align="center">

**"Quality is not an act, it is a habit" - Aristotle**

[⬅️ Volver al Portfolio Principal](../README.md)

</div>
