# Rueda_de_Hamburgo

Aplicación de escritorio para el análisis del ensayo de Rueda de Hamburgo (Hamburg Wheel Tracking Test, **AASHTO T 324**), orientada a profesionales y técnicos en ingeniería de pavimentos.  
Facilita la detección del punto de flujo (**Nsip**) en mezclas asfálticas y la visualización técnica de resultados mediante controles sencillos e intuitivos.

Link para descarga:
https://github.com/germancruzram/RUEDA_CARGADA_HAMBURGO/releases/download/RUEDA_DE_HAMBURGO_AASHTO_T324/RuedaHamburgo.rar

## Características principales

### 🧪 Procesamiento de datos
- Importación de archivos **CSV** y **Excel (XLSX)**.
- Lectura robusta de números (soporta `,` o `.` como separador decimal y separadores de miles).
- Manejo de **1 o 2 canales** (Izquierda, Derecha) y cálculo de **Promedio**.

### 📐 Detección del punto de flujo (Nsip)
- Método operativo en la interfaz: **“tangents reverse”** (proyección inversa de dos tangentes en etapas inicial y final).
- Cálculo de **ε@Nsip** y marcación visual del Nsip en la gráfica.
- Línea de **N objetivo (N0)** con cálculo **ε@N0**.

### 🎚️ Suavizado y representación
- Suavizado por **media móvil (moving average)** o **interpolación PCHIP** (cúbica hermítica preservadora de forma).
- Control de ventana de suavizado ajustable.
- Visualización con **Matplotlib** y barra de herramientas integrada (zoom, pan, guardar imagen, etc.).

### 🗂️ Gestión de proyectos
Se permite guardar y abrir proyectos en formato JSON propio (`.hwpj`), preservando:
- Datos cargados
- Parámetros de análisis
- Canal seleccionado
- Resultados detectados (cuando corresponda)

---

## Formato de proyecto (.hwpj)

Archivo JSON que encapsula:
- Rutas o copia de los datos
- Configuración de suavizado
- Método de detección
- Resultado Nsip (si ya fue calculado)

Ejemplo conceptual:
```json
{
  "version": "1.0",
  "canales": ["Izquierda", "Derecha"],
  "metodo_nsip": "tangents_reverse",
  "parametros": { "suavizado": "moving_average", "ventana": 7 },
  "resultado": { "Nsip": 5634, "epsilon_Nsip": 7.42 },
  "ruta_datos": "data/datos50.xlsx"
}
```

## 🤝**Contribuciones y recomendaciones**

Son bienvenidas. En mi perfil encuentran mi contacto

## 👨‍💻**Autor**

German Ahmed Cruz Ramírez  
[LinkedIn](https://www.linkedin.com/in/german-cruz-ram-in24/)

---

Si crees útil esta herramienta para el análisis del ensayo de Rueda de Hamburgo (AASHTO T 324), no olvides dejar una estrella ⭐ en el repositorio.
