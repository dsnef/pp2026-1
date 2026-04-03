# Ganado Saludable: Detección temprana de enfermedades bovinas

## Metodología

Con base en el Problema Prototípico, realizamos un acercamiento metodológico
adaptado basado en Hernández Sampieri (2014) para desarrollar un artículo de
divulgación. Los pasos son:

1. **Planteamiento del problema.** Se define un problema a investigar y se
   especifican los objetivos y las preguntas que orientarán la investigación.
2. **Revisión de la literatura.** Se estudia lo que se ha escrito sobre el tema
   para incorporar lo que resulte útil y conocer qué contribuciones se pueden
   hacer.
3. **Desarrollo del marco teórico.** Se elige o desarrolla una teoría o un
   conjunto de categorías de análisis para guiar la investigación.
4. **Formulación de hipótesis.** Se presenta una respuesta tentativa sobre el
   problema planteado, que deberá ser comprobada o refutada al final.
5. **Diseño de la investigación.** Se definen el método y las técnicas para
   obtener, analizar e interpretar los datos.
6. **Selección de la muestra o población.** Se define la muestra de la que se
   obtendrán los datos para cumplir los objetivos.
7. **Recolección de datos.** Se implementan las técnicas para obtener los datos
   necesarios según criterios aceptados por la comunidad científica.
8. **Análisis de datos.** Se procesan y analizan los datos obtenidos, ya sea
   mediante procedimientos estadísticos o mediante un examen crítico e
   interpretativo. Se evalúa si los datos confirman o refutan la hipótesis.
9. **Redacción del informe.** Se redacta un informe final con los pasos
   seguidos, los procedimientos implementados y los resultados obtenidos.


## Flujo de búsqueda de fuentes: de lo local a lo internacional

La búsqueda de bases de datos y bibliografía sigue una lógica deliberada:
primero se agotan las fuentes nacionales mexicanas y luego se amplía hacia
contextos internacionales. Esta secuencia hace la investigación más defendible:
primero conocemos nuestro problema en su propio contexto, luego buscamos
marcos técnicos y soluciones documentadas en el mundo.

| Capa | Fuentes | Uso principal |
|---|---|---|
| 🇲🇽 Nacional | SIAP, SENASICA, INIFAP, FIRA, INEGI, SciELO México | Contexto, epidemiología, datos de inventario |
| 🌐 Internacional | FAO, USDA, Kaggle, Zenodo, PubMed, Frontiers | Marco técnico, algoritmos, rangos fisiológicos |

Donde no existe equivalente nacional publicado (por ejemplo, rangos fisiológicos
de PLF), se usa fuente internacional con nota explícita de adaptabilidad al
contexto mexicano.

## Registro de fuentes

| # | Fuente | Autor(es) | Año | Origen | Tipo | Sección donde se usa | Disponible | Cita APA |
|---|---|---|---|---|---|---|---|---|
| 1 | SIAP inventario bovino | SADER | 2023 | MX | Datos abiertos | 2.1 | Sí (CSV) | — |
| 2 | SENASICA brucelosis | SENASICA | 2020 | MX | Informe oficial | 2.2 | Sí (PDF) | — |
| 3 | FIRA panorama bovino | FIRA | 2022 | MX | Informe sectorial | 2.1 | Sí (PDF) | ✓ |
| 4 | Agrolatam GBN | Agro Latam | 2026 | MX | Nota periodística | 2.3 | Sí (URL) | ✓ |
| 5 | Steensels et al. rumia | Steensels et al. | 2017 | Internacional | Journal arbitrado | 4.4 | Sí (PDF) | ✓ |

## Reparto sugerido de responsabilidades por perfil

| Integrante | Área principal | Herramientas clave | 
|---|---|---|
| Perfil datos | Búsqueda y limpieza de datasets (MX → intl) | GitHub /data, Sheets hoja fuentes | 
| Perfil redacción | Integración del documento principal | Google Docs, rama redaccion | 
| Perfil análisis | EDA, variables, modelo E-R | GitHub /notebooks, Sheets EDA | 
| Perfil coordinación | Tracker, minutas, coherencia del documento | Sheets tracker, README

## Estructura del repositorio
```
bovinealert-investigacion/
│
├── README.md
│
├── /docs                        ← secciones del documento en markdown
│   ├── 01_introduccion.md
│   ├── 02_marco_referencial.md
│   ├── 03_modelado_datos.md
│   ├── 04_analisis_viabilidad.md
│   └── 05_propuesta_mva.md
│
├── /data
│   ├── /mx                      ← SIAP, SENASICA, INEGI, FIRA
│   │   └── README_fuentes.md    ← qué es cada archivo, origen, fecha de descarga
│   └── /internacional           ← Kaggle, FAO, journals
│       └── README_fuentes.md
│
├── /notebooks                   ← análisis exploratorio y modelos
│   ├── 01_eda.ipynb
│   └── 02_modelo_base.ipynb
│
├── /bibliografia
│   └── referencias.md           ← lista APA 7 unificada
│
└── /assets                      ← figuras, diagramas, imágenes del artículo
```

## Estructura de Google Drive
```
📁 BovineAlert · Equipo 1 · Grupo 403
│
├── 📁 0. Gestión
│   ├── Tracker de avance (Sheets)
│   └── Minutas de reunión (Doc)
│
├── 📁 1. Documento principal
│   └── Investigación_4to_semestre (Doc)
│
├── 📁 2. Bibliografía
│   ├── Registro de fuentes (Sheets)
│   └── 📁 PDFs/
│
├── 📁 3. Datos
│   ├── 📁 Nacional
│   └── 📁 Internacional
│
├── 📁 4. Análisis
│   ├── EDA borrador (Sheets)
│   └── 📁 Visualizaciones/
│
└── 📁 5. Entregables finales
    ├── Artículo de divulgación (Doc)
    └── Presentación (Slides)
```

## Flujo de trabajo en Git

Nadie hace push directo a `main`. Todo entra por Pull Request.
```
main
 ├── datos-mx          → búsqueda y limpieza de fuentes nacionales
 ├── datos-intl        → búsqueda y limpieza de fuentes internacionales
 ├── modelado          → modelo E-R, variables, definiciones
 └── redaccion         → integración del documento principal
```

## Convenciones de commits
```
feat: nueva sección o dataset agregado
fix:  corrección de cita o error de contenido
data: nuevo archivo de datos incorporado
docs: actualización de documentación o README
```
