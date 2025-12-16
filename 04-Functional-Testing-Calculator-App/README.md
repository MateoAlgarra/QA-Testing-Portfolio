# Testing Funcional - Aplicación Móvil Calculator

> **Ejecución y documentación de pruebas funcionales en app móvil de cálculo laboral**

## 📱 Descripción del Proyecto

Ejecución de **pruebas funcionales** completas en la aplicación móvil "Calculator - Calculadora de Quincena Laboral", herramienta profesional para trabajadores colombianos que calcula quincenas laborales según legislación vigente.

**Aplicación:** Calculator v2.0 (Android/iOS)  
**Tipo de Prueba:** Funcional (Caja Negra)  
**Curso:** SENA - Manejo de Pruebas de Software  
**Fecha:** Noviembre 2025

---

## 🎯 Objetivo de las Pruebas

Validar que cada funcionalidad de la aplicación móvil cumpla con los requerimientos establecidos y realice correctamente los cálculos laborales según la normatividad colombiana vigente.

---

## 📋 Alcance del Testing

### Funcionalidades Probadas

**1. Módulo de Horas Extra**
- Cálculo de recargo diurno (25%)
- Cálculo de recargo nocturno (75%)
- Validación de rangos horarios (6:00 PM - 6:00 AM)

**2. Módulo de Horas Dominicales y Festivas**
- Recargo dominical (75%)
- Recargo festivo (75%)
- Cálculo combinado (extra + dominical/festiva)

**3. Módulo de Auxilio de Transporte**
- Cálculo automático según salario
- Validación de umbral legal
- Integración con salario total

**4. Módulo de Deducciones**
- Pensión (4% del salario)
- Salud (4% del salario)
- Otras deducciones configurables

**5. Cálculo Final de Quincena**
- Integración de todos los módulos
- Validación de fórmula completa
- Presentación de resultados

---

## 🧪 Metodología de Pruebas

### Tipo de Prueba: Funcional

**Técnica:** Caja Negra  
**Enfoque:** Validación de salidas contra entradas esperadas  
**Herramientas:**
- Aplicación móvil Calculator v2.0
- Smartphone Android/iOS actualizado
- Microsoft Word (documentación)
- Captura de pantalla nativa

---

## 📊 Casos de Prueba Ejecutados

### Resumen de Ejecución

| Módulo | Casos de Prueba | Aprobados | Fallidos | % Éxito |
|--------|----------------|-----------|----------|---------|
| Horas Extra Diurnas | 5 | 4 | 1 | 80% |
| Horas Extra Nocturnas | 5 | 5 | 0 | 100% |
| Dominicales/Festivos | 4 | 3 | 1 | 75% |
| Auxilio Transporte | 3 | 3 | 0 | 100% |
| Deducciones | 4 | 4 | 0 | 100% |
| Cálculo Final | 6 | 5 | 1 | 83% |
| **TOTAL** | **27** | **24** | **3** | **89%** |

---

## 🐛 Defectos Identificados

### Defecto #1: Error en Cálculo de Horas Extra Diurnas

**Severidad:** Media  
**Prioridad:** Alta

**Descripción:**  
Al ingresar 4 horas extra diurnas con salario de $1,500,000, el sistema calcula $31,250 cuando debería ser $31,250 (recargo 25%).

**Pasos para Reproducir:**
1. Abrir módulo "Horas Extra"
2. Ingresar salario: $1,500,000
3. Ingresar 4 horas extra diurnas
4. Calcular

**Resultado Esperado:** $31,250  
**Resultado Obtenido:** $28,125 (error de redondeo)

**Evidencia:** Screenshot incluido en documento

---

### Defecto #2: Validación Incorrecta de Dominicales

**Severidad:** Media  
**Prioridad:** Media

**Descripción:**  
Sistema permite ingresar más de 30 días dominicales en un mes, lo cual es lógicamente imposible.

**Recomendación:** Implementar validación max = 4-5 domingos/mes

---

### Defecto #3: Interfaz de Usuario - Botón "Limpiar" No Funciona

**Severidad:** Baja  
**Prioridad:** Baja

**Descripción:**  
El botón "Limpiar campos" no resetea todos los campos del formulario.

**Impacto:** Usuario debe reiniciar app para limpiar completamente

---

## ✅ Validaciones Realizadas

### Validación de Fórmulas

**1. Valor Hora Ordinaria:**
```
Valor Hora = Salario Mensual / 240 horas
```
✅ Validado correctamente

**2. Hora Extra Diurna (Recargo 25%):**
```
HED = Valor Hora × 1.25 × Cantidad de Horas
```
⚠️ Requiere ajuste de redondeo

**3. Hora Extra Nocturna (Recargo 75%):**
```
HEN = Valor Hora × 1.75 × Cantidad de Horas
```
✅ Validado correctamente

**4. Auxilio de Transporte 2025:**
```
Si Salario ≤ $2,899,999 → Auxilio = $200,000
Si Salario > $2,899,999 → Auxilio = $0
```
✅ Validado correctamente

**5. Deducciones:**
```
Pensión = Salario × 4%
Salud = Salario × 4%
Total Deducciones = Pensión + Salud + Otras
```
✅ Validado correctamente

---

## 📈 Análisis de Calidad

### Cumplimiento de Requisitos

**Requisitos Funcionales:** 89% cumplidos  
**Usabilidad:** Buena (interfaz clara y simple)  
**Performance:** Excelente (cálculos instantáneos)  
**Compatibilidad:** Probado en Android (versión específica)

### Recomendaciones

1. ✅ **Corregir redondeo** en cálculos de horas extra
2. ✅ **Implementar validaciones** de rangos lógicos
3. ✅ **Reparar botón Limpiar** para mejor UX
4. ✅ **Agregar tooltips** explicativos para usuarios
5. ✅ **Incluir ejemplos** de cálculo en la app

---

## 🎯 Conclusiones

### Fortalezas de la Aplicación

- ✅ Interfaz intuitiva y fácil de usar
- ✅ Cálculos rápidos y eficientes
- ✅ Cobertura completa de conceptos laborales colombianos
- ✅ Presentación clara de resultados

### Áreas de Mejora

- ⚠️ Precisión en redondeos de cálculos
- ⚠️ Validaciones de rangos de entrada
- ⚠️ Funcionalidad completa de botones de interfaz

### Recomendación Final

**La aplicación es apta para uso con correcciones menores.** Se recomienda implementar los 3 defectos identificados antes del lanzamiento oficial.

---

## 📁 Recursos

- 📄 [Documento Completo de Pruebas (PDF)](./Taller3_Calculator_Mateo_Algarra.pdf)
- 📸 Screenshots de ejecución de pruebas
- 📋 Casos de prueba detallados

---

## 🎯 Competencias Demostradas

- ✅ Ejecución de pruebas funcionales manuales
- ✅ Diseño de casos de prueba basados en requisitos
- ✅ Validación de fórmulas y cálculos complejos
- ✅ Identificación y documentación de defectos
- ✅ Uso de formato Bugzilla para reportes
- ✅ Análisis de calidad y recomendaciones
- ✅ Testing de aplicaciones móviles

---

## 📋 Formato de Documentación

El proyecto siguió el **formato Bugzilla del SENA** para documentación de defectos:
- Descripción clara del problema
- Pasos detallados para reproducir
- Resultado esperado vs. obtenido
- Severidad y prioridad
- Evidencia visual (screenshots)

---

<div align="center">

**"Testing shows the presence, not the absence of bugs" - Edsger Dijkstra**

[⬅️ Volver al Portfolio Principal](../README.md)

</div>
