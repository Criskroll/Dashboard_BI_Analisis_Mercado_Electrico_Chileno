# ⚡ Dashboard de Inteligencia de Negocios: Análisis del Mercado Eléctrico / Mes Julio 2026

Este repositorio contiene el desarrollo del modelo de datos y dashboard interactivo en **Power BI** para la auditoría operativa del mercado eléctrico, enfocado en la relación entre **Generación por Tecnología** y **Demanda Sistémica**.

---

## 🛠️ Arquitectura y Modelado de Datos

El proyecto implementa un modelo en estrella (**Star Schema**) optimizado para análisis analítico:
* **Tablas de Hechos:** Transacciones horarias de despacho por central/tecnología y registros de demanda del sistema.
* **Tablas de Dimensiones:** `Dim_Tecnologia` (clasificación ERNC vs. Convencional) y `Dim_Calendario` (línea temporal común).

---

## 📊 Métricas Clave Desarrolladas (DAX)

### 1. Participación ERNC %
Calcula el porcentaje relativo de energía limpia inyectada al sistema por fuentes Renovables No Convencionales (Solar Fotovoltaica, Eólica, Biomasa, Mini Hidro, CSP, Geotérmica):

$$\text{Participación ERNC \%} = \frac{\text{Generación Total ERNC (MWh)}}{\text{Generación Total Sistema (MWh)}}$$

* **Resultado Auditado:** **`41.87%`** del total despachado en el periodo.

### 2. Margen Promedio de Reserva (MWh)
Mide la holgura promedio del sistema entre la capacidad de generación despachada y la demanda real requerida a nivel horario:

$$\text{Margen Promedio} = \text{Promedio}(\text{Generación Total Horaria} - \text{Demanda Horaria})$$

* **Resultado Auditado:** **`553.80 mil MWh`** de holgura operativa.

---

## 🔍 Análisis Operativo & Causa Raíz

A partir de las visualizaciones y filtros temporales del dashboard, se determinó el comportamiento del sistema ante fluctuaciones de despacho:

1. **Liderazgo Renovable:** La generación fotovoltaica (**19.33%**) y eólica (**17.36%**) constituyen los pilares de la transición energética del sistema, cubriendo más del 36% de la demanda global por sí solas.
2. **Ventana de Estrés Sistémico (Días 18 al 20):** 
   * Se identificó una caída sostenida en la radiación solar y el recurso eólico durante esta ventana temporal.
   * **Causa Raíz & Respuesta:** La contracción de la oferta renovable provocó un estrechamiento del margen de reserva, activando de inmediato el despacho de respaldo de **Hidráulica de Embalse** y **Gas Natural** para garantizador el balance de frecuencia y la seguridad del suministro.

---

## 📁 Archivos Incluidos en este Repositorio

* `DB_for_EDF-Power_Cristhofer_Guzman_Kroll.pbix`: Archivo fuente ejecutable con el modelo relacional y fórmulas DAX.
* `Reporte_Ejecutivo_Mercado_Electrico.pdf`: Exportación ejecutiva vectorizada en alta resolución para revisión rápida.

---
**Desarrollado por:** Cristhofer Guzmán Kroll  
*Estudiante de Ingeniería en Informática | Analytics & Data Engineering*
