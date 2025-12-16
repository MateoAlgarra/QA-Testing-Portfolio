# Gestión de Cambios y Pruebas Finales - Calculator App

> **Documentación sistemática de gestión de cambios y priorización de defectos**

## 📋 Descripción del Proyecto

Documentación completa del **proceso de gestión de cambios** identificados durante el ciclo de pruebas de la aplicación Calculator. Este proyecto demuestra capacidad de análisis, priorización e implementación de ajustes necesarios para garantizar la calidad del software.

**Aplicación:** Calculator - Calculadora de Quincena Laboral  
**Tipo de Actividad:** Change Management & Final Testing  
**Curso:** SENA - Manejo de Pruebas de Software (Actividad 4)  
**Fecha:** Noviembre 2025

---

## 🎯 Objetivos del Proyecto

### Objetivo General
Gestionar de manera sistemática y documentada todos los cambios identificados en la aplicación Calculator, priorizando aquellos que impactan directamente la funcionalidad, precisión de cálculos y experiencia del usuario.

### Objetivos Específicos
1. Analizar y clasificar incidentes por impacto y prioridad
2. Proponer soluciones técnicas fundamentadas
3. Planificar implementación de cambios
4. Establecer cronograma de ejecución
5. Definir criterios de validación post-cambio

---

## 🔍 Proceso de Gestión de Cambios

### Metodología Aplicada

```
Identificación → Registro → Análisis → Clasificación
       ↓                                     ↓
  Planificación ← Aprobación ← Priorización
       ↓
Implementación → Verificación → Cierre
```

### Clasificación de Cambios

| Categoría | Criterio | Tiempo de Resolución |
|-----------|----------|---------------------|
| **Crítico** | Afecta cálculos o funcionalidad principal | Inmediato (1-2 días) |
| **Alto** | Impacta experiencia del usuario | 3-5 días |
| **Medio** | Mejoras de interfaz o usabilidad | 1 semana |
| **Bajo** | Ajustes cosméticos o sugerencias | Próxima versión |

---

## 📊 Registro de Cambios Identificados

### Cambio #1: Corrección de Redondeo en Horas Extra Diurnas

**Categoría:** Crítico  
**Prioridad:** Alta  
**Impacto:** Cálculos financieros incorrectos

**Problema Identificado:**
```
Entrada: 4 horas extra diurnas, salario $1,500,000
Resultado Actual: $28,125
Resultado Esperado: $31,250
Diferencia: $3,125 (error de 10%)
```

**Análisis de Causa Raíz:**
Función de redondeo aplicada antes de multiplicar por cantidad de horas en lugar de después.

**Solución Propuesta:**
```javascript
// ANTES (Incorrecto):
const valorHora = Math.round(salario / 240);
const horaExtraDiurna = valorHora * 1.25 * cantidadHoras;

// DESPUÉS (Correcto):
const valorHora = salario / 240;
const horaExtraDiurna = Math.round(valorHora * 1.25 * cantidadHoras);
```

**Validación Post-Cambio:**
- Suite de 10 casos de prueba con diferentes salarios
- Comparación con cálculos manuales
- Aprobación por QA y usuario final

---

### Cambio #2: Validación de Rangos de Entrada

**Categoría:** Alto  
**Prioridad:** Alta  
**Impacto:** Prevención de errores de usuario

**Problema Identificado:**
Sistema permite valores ilógicos:
- Días dominicales > 31 en un mes
- Horas trabajadas > 24 en un día
- Salarios negativos

**Solución Propuesta:**

**Validación de Días Dominicales:**
```javascript
if (diasDominicales < 0 || diasDominicales > 5) {
  showError("Los días dominicales deben estar entre 0 y 5");
  return false;
}
```

**Validación de Horas:**
```javascript
if (horasTrabajadas < 0 || horasTrabajadas > 24) {
  showError("Las horas deben estar entre 0 y 24");
  return false;
}
```

**Validación de Salario:**
```javascript
const SALARIO_MINIMO_2025 = 1423500;
if (salario < SALARIO_MINIMO_2025) {
  showWarning("El salario ingresado es menor al mínimo legal");
}
```

---

### Cambio #3: Corrección de Botón "Limpiar Campos"

**Categoría:** Medio  
**Prioridad:** Media  
**Impacto:** Experiencia de usuario

**Problema Identificado:**
Botón "Limpiar" no resetea todos los campos del formulario.

**Solución Propuesta:**
```javascript
function limpiarCampos() {
  document.getElementById('salario').value = '';
  document.getElementById('horasExtra').value = '';
  document.getElementById('diasDominicales').value = '';
  document.getElementById('deducciones').value = '';
  // Limpiar también resultados
  document.getElementById('resultado').innerHTML = '';
  // Resetear validaciones
  clearValidationErrors();
}
```

---

### Cambio #4: Mejora de Mensajes de Error

**Categoría:** Medio  
**Prioridad:** Media  
**Impacto:** Usabilidad

**Problema Identificado:**
Mensajes de error genéricos que no ayudan al usuario.

**Solución Propuesta:**

**ANTES:**
```
"Error en el cálculo"
```

**DESPUÉS:**
```
"Error: El salario debe ser un número mayor a $1,423,500 (salario mínimo legal 2025)"
```

**Beneficios:**
- Usuario entiende exactamente qué corregir
- Reduce frustración
- Educativo (menciona salario mínimo legal)

---

### Cambio #5: Tooltips Informativos

**Categoría:** Bajo  
**Prioridad:** Baja  
**Impacto:** Experiencia educativa

**Solución Propuesta:**
Agregar tooltips explicativos:
- "Horas Extra Diurnas: 6:00 AM - 6:00 PM (Recargo 25%)"
- "Horas Extra Nocturnas: 6:00 PM - 6:00 AM (Recargo 75%)"
- "Auxilio de Transporte: Solo aplica para salarios ≤ $2,899,999"

---

## 📅 Cronograma de Implementación

### Fase 1: Cambios Críticos (Semana 1)
- ✅ Lunes-Martes: Corrección de redondeo (#1)
- ✅ Miércoles-Jueves: Implementación de validaciones (#2)
- ✅ Viernes: Testing de cambios críticos

### Fase 2: Cambios de Alta Prioridad (Semana 2)
- ✅ Lunes-Martes: Corrección botón limpiar (#3)
- ✅ Miércoles: Mejora de mensajes (#4)
- ✅ Jueves-Viernes: Regression Testing

### Fase 3: Mejoras de UX (Semana 3)
- ✅ Lunes-Miércoles: Implementación tooltips (#5)
- ✅ Jueves: Testing final completo
- ✅ Viernes: Release v2.1

---

## 🧪 Plan de Validación Post-Cambios

### Pruebas de Regresión

**Alcance:**
- Re-ejecutar todos los 27 casos de prueba originales
- Verificar que cambios no introdujeron nuevos defectos
- Validar funcionalidad no modificada

**Criterio de Éxito:**
- 100% de casos de prueba aprobados
- 0 defectos críticos o altos
- Performance mantenida o mejorada

### Pruebas de Validación de Cambios

| Cambio | Casos de Prueba Nuevos | Responsable |
|--------|------------------------|-------------|
| Corrección redondeo | 10 casos con diversos salarios | QA + Dev |
| Validaciones | 15 casos límite | QA |
| Botón limpiar | 5 casos de flujo | QA |
| Mensajes de error | 8 casos de validación | UX + QA |

---

## 📊 Métricas de Éxito

### KPIs del Proyecto

**Antes de Cambios:**
- Tasa de éxito de pruebas: 89%
- Defectos críticos: 1
- Defectos medios: 2

**Después de Cambios (Objetivo):**
- Tasa de éxito de pruebas: 100%
- Defectos críticos: 0
- Defectos medios: 0

**Tiempo Total de Implementación:** 3 semanas  
**Inversión de QA:** ~40 horas  
**Inversión de Development:** ~60 horas

---

## 💡 Lecciones Aprendidas

### 1. **Importancia del Análisis de Causa Raíz**
No solo identificar el síntoma, sino entender por qué ocurrió el defecto.

### 2. **Priorización Clara es Esencial**
Matriz de impacto/prioridad ayuda a enfocar esfuerzos en lo más crítico.

### 3. **Validaciones Tempranas Previenen Defectos**
Validar entrada de usuario reduce errores downstream.

### 4. **Documentación Facilita Seguimiento**
Registro estructurado permite auditoría y aprendizaje futuro.

### 5. **Comunicación con Stakeholders**
Informar claramente el impacto de cada cambio y timeline.

---

## 📈 Impacto del Proyecto

### Mejoras Cuantificables

**Calidad:**
- ↑ 11% en tasa de éxito de pruebas (89% → 100%)
- ↓ 100% en defectos críticos (1 → 0)

**Usabilidad:**
- ↑ Claridad de mensajes de error
- ↑ Prevención de errores de usuario
- ↑ Facilidad de uso

**Confiabilidad:**
- ↑ Precisión de cálculos financieros
- ↑ Confianza del usuario en resultados

---

## 📁 Recursos

- 📄 [Documento Completo de Gestión de Cambios (PDF)](./Taller4_Calculator_Mateo_Algarra.pdf)
- 📋 Registro detallado de cambios
- 📊 Plan de validación
- 📅 Cronograma de implementación

---

## 🎯 Competencias Demostradas

- ✅ Gestión sistemática de cambios de software
- ✅ Análisis de causa raíz de defectos
- ✅ Priorización basada en impacto y riesgo
- ✅ Propuesta de soluciones técnicas fundamentadas
- ✅ Planificación de implementación
- ✅ Definición de criterios de validación
- ✅ Gestión de cronogramas de proyecto
- ✅ Documentación profesional de procesos

---

## 📋 Relación con Proyecto Anterior

Este proyecto es la **continuación natural** del Taller 3 (Testing Funcional):

**Taller 3:** Identificación de defectos → **Taller 4:** Gestión de correcciones

Demuestra el **ciclo completo de QA:**
```
Testing → Identificación → Análisis → Priorización → 
Corrección → Validación → Release
```

---

<div align="center">

**"Change is inevitable. Growth is optional" - John C. Maxwell**

[⬅️ Volver al Portfolio Principal](../README.md)

</div>
