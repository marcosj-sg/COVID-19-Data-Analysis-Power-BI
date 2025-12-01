# COVID-19-Data-Analysis-Power-BI

## **Descripción del Proyecto**

Este proyecto es un **dashboard interactivo en Power BI** diseñado para **analizar el impacto global del COVID-19** utilizando datos de fuentes públicas. El análisis incluye KPIs clave, como **casos confirmados**, **muertes**, **tasa de mortalidad**, y **afectación global**. A través de visualizaciones interactivas, el proyecto permite explorar la **evolución temporal** de la pandemia, el **análisis geográfico** y las **tendencias demográficas**.

---

## **Fuentes de Datos**

- **COVID-19 Data Repository by Johns Hopkins University**  
  [Enlace al repositorio de datos COVID-19](https://github.com/CSSEGISandData/COVID-19)
  - `time_series_covid19_confirmed_global.csv`
  - `time_series_covid19_deaths_global.csv`

- **Wikipedia - Lista de países y dependencias por población**  
  [Enlace a Wikipedia](https://en.wikipedia.org/wiki/List_of_countries_and_dependencies_by_population)

---

## **Modelo de Datos**

### **Tablas de Dimensiones**

1. **D_Tiempo (Dimensión Temporal)**  
   - **Campos**: Date, Day, Month, Year, Quarter, etc.

2. **D_Paises (Dimensión Geográfica)**  
   - **Campos**: Country/Region, Population, % of World, Top 10 Filter

### **Tablas de Hechos**

1. **H_Covid19_Confirmed (Casos Confirmados)**  
   - **Campos**: Date, Country/Region, Confirmed (Casos confirmados)

2. **H_Covid19_Deaths (Muertes Confirmadas)**  
   - **Campos**: Date, Country/Region, Deaths (Muertes)

### **Relaciones**

- **D_Tiempo[Date] 1:N → H_Covid19_Confirmed[Date]**
- **D_Tiempo[Date] 1:N → H_Covid19_Deaths[Date]**
- **D_Paises[Country/Region] 1:N → H_Covid19_Confirmed[Country/Region]**
- **D_Paises[Country/Region] 1:N → H_Covid19_Deaths[Country/Region]**

---

## **KPIs y Medidas Implementadas**

### **KPIs Principales**

- **Población Total**: Población total por país.
- **Confirmados**: Suma de casos confirmados por país.
- **Muertes**: Suma de muertes totales por país.
- **Afectación (%)**: Confirmados / Población.
- **Tasa de Mortalidad (%)**: Muertes / Confirmados.

### **Medidas de Análisis Temporal**

- **Crecimiento Diario de Casos**: Diferencia porcentual de los confirmados en el día seleccionado respecto al día anterior.
- **Crecimiento Diario de Muertes**: Diferencia porcentual de los fallecimientos en el día seleccionado respecto al día anterior.
- **Media Móvil (7 días)**: Promedio de los últimos 7 días de casos y muertes.

### **Medidas de Tendencia**

- **Índice de Severidad**: Combinación de la tasa de afectación y mortalidad.
- **Rango Global de Mortalidad**: Clasificación de países según la tasa de mortalidad.
- **Tendencia de Casos**: Indicador de la tendencia de crecimiento de casos.

---

## **Dashboard en Power BI**

### **Pantalla 1: Vista Global**

- **Mapa interactivo** con coloración por tasa de mortalidad.
- **10 Tarjetas KPI** para visualizar la población, casos confirmados, muertes y afectación global.
- **Segmentadores** para analizar el impacto en países seleccionados.

### **Pantalla 2: Análisis Demográfico**

- **Gráfico de dispersión** de población vs tasa de afectación.
- **Tabla detallada** con rankings de países por casos confirmados, muertes y tasa de mortalidad.
- **Gráfico de barras** mostrando la diferencia en la representación de casos por país.

### **Pantalla 3: Evolución Temporal**

- **Gráfico de líneas** mostrando la evolución de casos confirmados y muertes a lo largo del tiempo.
- **KPIs de tendencia**: Tasa de crecimiento semanal, media móvil de 7 días, pico máximo histórico de casos y muertes.
- **Heatmap mensual de casos**.

---

## **Instrucciones de Uso**

### **Requisitos**

- Power BI Desktop instalado.
- Acceso a los archivos CSV de Johns Hopkins University y Wikipedia para actualizar los datos.


---

## **Consideraciones Técnicas**

### **Best Practices Implementadas**

- **Modelo Dimensional (Star Schema)**: Se utiliza para organizar los datos de manera eficiente y escalable.
- **Optimización en DAX**: Las medidas DAX están diseñadas para un rendimiento óptimo en grandes volúmenes de datos.
- **Interactividad**: Los filtros y segmentadores permiten explorar los datos de manera flexible y dinámica.
- **Automatización**: El flujo de datos se actualiza automáticamente desde Azure Blob Storage, lo que permite que los análisis estén siempre actualizados.

---

## **Próximos Pasos**

### **Prioridad Alta**
1. Completar la integración de más fuentes de datos, como información de vacunación y nuevas variantes.
2. Agregar más gráficos de series temporales para mejorar el análisis predictivo.

### **Prioridad Media**
1. Optimización del diseño y ajuste de colores para mayor accesibilidad.
2. Revisión de consistencia de datos.
3. Documentación final del proyecto.

---

### **Conclusión**

Este proyecto proporciona una solución integral para el análisis de la pandemia de COVID-19, permitiendo visualizar su impacto global a través de diferentes métricas, con un modelo de datos dinámico y escalable. Las fuentes de datos están automáticamente actualizadas desde **Azure Cloud Services**, lo que asegura que el análisis esté siempre al día.

---

**Instrucciones adicionales:**
*Puedes actualizar los datos desde la fuente de [Johns Hopkins University COVID-19 Data Repository](https://github.com/CSSEGISandData/COVID-19) para ver la evolución más reciente.*

