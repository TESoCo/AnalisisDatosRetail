# Análisis de Factores de Comportamiento en NovaRetail+

## Descripción del proyecto

Este proyecto realiza un análisis correlacional (exploratorio) sobre el comportamiento de clientes de NovaRetail+, una plataforma de comercio electrónico en Latinoamérica con millones de usuarios.

El objetivo principal es responder a la pregunta del equipo de Crecimiento y retención para el cierre de 2024:

> ¿Qué factores del comportamiento del cliente están más fuertemente asociados con el ingreso anual generado?

> Nota metodológica: Este es un análisis correlacional. Correlación ≠ causalidad. Los hallazgos describen asociaciones, no relaciones causa-efecto.

---

## Objetivos

- Validar la carga y calidad del dataset.
- Explorar la estructura y distribución de las variables.
- Identificar qué variables del comportamiento del cliente presentan mayor asociación con `ingreso_anual`.
- Documentar supuestos y decisiones de limpieza de datos.

---

## Descripción del dataset

El conjunto de datos contiene 15,000 registros y 12 columnas, sin valores nulos.

| Columna | Descripción |
|---|---|
| `id_cliente` | Identificador único del cliente |
| `edad` | Edad del cliente |
| `nivel_ingreso` | Ingreso anual estimado del cliente |
| `visitas_mes` | Número de visitas a la app/sitio web durante el mes |
| `compras_mes` | Número de compras realizadas en el mes |
| `gasto_publicidad_dirigida` | Gasto en anuncios asignado al usuario |
| `satisfaccion` | Calificación de satisfacción (escala 1–5) |
| `miembro_premium` | Suscripción premium (1) o no (0) |
| `abandono` | Cliente abandonó la plataforma (1) o no (0) |
| `tipo_dispositivo` | Dispositivo utilizado (móvil, escritorio, tablet) |
| `region` | Región geográfica (norte, sur, este, oeste) |
| `ingreso_anual` | Ingreso anual generado por el cliente para la empresa (métrica principal) |

---

## Metodología

### Sección 1 — Carga y exploración inicial
- Importación de librerías (`pandas`, `numpy`, `seaborn`, `matplotlib`).
- Carga del dataset y verificación de tipos de datos, valores nulos y rangos generales.
- Inspección de las primeras filas para entender la estructura.

### Sección 2 — Preparación de datos y supuestos
- Corrección de tipo: `edad` convertida de `float64` a `int64`.
- Variables numéricas identificadas: `edad`, `nivel_ingreso`, `visitas_mes`, `compras_mes`, `gasto_publicidad_dirigida`, `satisfaccion`, `ingreso_anual`.
- Variables binarias: `miembro_premium`, `abandono` (codificadas 0/1, sin transformación adicional).
- Variables categóricas: `id_cliente`, `tipo_dispositivo`, `region`.
- Estadísticas descriptivas para detectar rangos, dispersión y posibles valores atípicos.

### Hallazgos preliminares de la exploración
- `ingreso_anual` presenta una distribución asimétrica: media ≈ 36.6, mediana ≈ 30.7, máximo 244.7, con un 25% de clientes en 0.
- `compras_mes` tiene mediana de 1 y máximo de 8, con un 25% de clientes sin compras en el mes.
- `abandono` afecta aproximadamente al 15% de los clientes.
- `miembro_premium` representa cerca del 14% de la base.

---

## Tecnologías utilizadas

- Python 3
- pandas — manipulación y análisis de datos
- numpy — operaciones numéricas
- matplotlib / seaborn — visualización

---

## Cómo usar este análisis en Jupyter Notebook

1. Descarga o clona el archivo `Case_Retail.ipynb` en tu equipo.

2. Verifica que tengas Jupyter Notebook instalado. Si no lo tienes, instálalo junto con las dependencias necesarias:
   ```
   pip install notebook pandas numpy matplotlib seaborn
   ```

3. Coloca el archivo del dataset (`novaretail_comportamiento_clientes_2024.csv`) en la ruta `/datasets/` o ajusta la ruta en la celda de carga del notebook según donde lo hayas guardado.

4. Inicia Jupyter Notebook desde la carpeta donde se encuentra el archivo:
   ```
   jupyter notebook
   ```

5. Abre `Case_Retail.ipynb` desde el navegador y ejecuta las celdas en orden, de arriba hacia abajo.

---

## Resultados esperados

El notebook produce:
- Un diagnóstico de calidad y estructura del dataset.
- Estadísticas descriptivas de todas las variables numéricas.
- Una base preparada para el análisis correlacional con `ingreso_anual`.
- Documentación explícita de supuestos y transformaciones aplicadas.

---

## Limitaciones y consideraciones

- Análisis correlacional: no permite establecer causalidad.
- Datos observacionales: pueden existir variables de confusión no medidas.
- Valores en cero: una proporción relevante de clientes tiene `ingreso_anual = 0`, lo que puede influir en las correlaciones.
- Dataset no incluido: por políticas de confidencialidad, los datos no se distribuyen con el repositorio.

---

## Autor

Jose Alfonso Taylor Marin
Proyecto 7 — Análisis de comportamiento de clientes
NovaRetail+ · Cierre 2024

---

## Licencia

Este proyecto se comparte con fines educativos y de portafolio. El dataset pertenece a NovaRetail+ y no se distribuye públicamente.
```
