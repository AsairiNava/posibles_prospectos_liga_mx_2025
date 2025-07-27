# Análisis de Prospectos Jóvenes para Equipos de la Liga MX

Este proyecto tiene como objetivo identificar a los mejores **jugadores jóvenes mexicanos** que podrían encajar como prospectos en cada uno de los equipos de la Liga MX, utilizando análisis de datos estadísticos y criterios de rendimiento individuales de los torneos Apertura 2024 y Clausura 2025.

## Objetivo del análisis

Los clubes del fútbol mexicano, como Chivas, Tigres, América y otros, necesitan identificar jóvenes talentos que no solo tengan buen rendimiento, sino que también se alineen con sus características tácticas, necesidades de posición y políticas internas (por ejemplo, Chivas solo puede contratar jugadores mexicanos).

Este análisis busca responder:

> *¿Qué jugadores jóvenes mexicanos tienen el mejor rendimiento actual y podrían encajar como refuerzos en otros equipos de la Liga MX?

## 📁 Estructura del proyecto

- `5_prospectos_para_equipos_liga_MX_básico.ipynb`: Notebook principal con el desarrollo completo del análisis.
- `README.md`: Este archivo.

## Fuente y complejidad de los datos

Los datos se obtuvieron de la plataforma pública **FBref** (vía Google Sheets), que proporcionan estadísticas detalladas por jugador:

- Minutos jugados (`Min`)
- Goles (`Gls`)
- Asistencias (`Ast`)
- Métricas esperadas (`xG`, `xAG`, etc.)
- Contribuciones por 90 minutos
- Edad, posición, nacionalidad y club

**Nivel de complejidad:** Medio-Alto  
El dataset contiene múltiples variables por jugador (más de 35 columnas) y requiere limpieza de datos, normalización por 90 minutos, filtrado condicional y agrupamiento inteligente para evaluar "fit" entre jugador y club.

## 🔍 Metodología utilizada

1. **Carga y limpieza de datos**  
   - Conversión de columnas a tipos correctos (e.g., `Min` a `float`)
   - Filtros para jugadores con más de 200 minutos jugados

2. **Filtrado de población objetivo**  
   - Jugadores mexicanos (`Nation == 'mx MEX'`)
   - Jugadores jóvenes (`Edad <= 25`)

3. **Cálculo de score de rendimiento**  
   - Suma ponderada de estadísticas normalizadas por 90 minutos

4. **Asignación de prospectos por equipo**  
   - Comparación de necesidades posicionales promedio por equipo
   - Exclusión de jugadores que ya están en el equipo de destino
   - Consideración especial para Chivas (solo mexicanos)

5. **Visualización con Matplotlib y Seaborn**  
   - Gráficos de distribución de edades, scores y comparaciones entre clubes

## Ejemplo de salida

Una tabla por equipo con los 5 prospectos más compatibles, por ejemplo:

| Equipo     | Posición | Jugador           | Score   | Edad | Club actual  |
|------------|----------|-------------------|---------|------|--------------|
| Guadalajara | DF       | Jesús Rivas        | 393.76 | 21   | Puebla       |
| Guadalajara | FW       | Alfonso Alvarado   | 1440.20| 24   | León         |
| ...        | ...      | ...               | ...     | ...  | ...          |

## Posibles mejoras

- Incluir variables económicas: valor de mercado, salario, cláusula
- Incorporar sistema de recomendación basado en similitud de estilo de juego
- ñadir validación con entrenadores o analistas deportivos
- Añadir contexto táctico de cada club (e.g., esquema táctico 4-3-3 vs 5-3-2)

## Créditos y herramientas utilizadas

- 🐍 Python (Pandas, NumPy, Seaborn, Matplotlib)
- 📊 Google Sheets para limpieza inicial
- 📦 Google Colab para correr el análisis
- 📘 FBref como fuente de datos estadísticos

## Contacto

¿Tienes sugerencias o ideas para mejorar este análisis?

Puedes escribirme por GitHub o a través de mi [LinkedIn]([https://www.linkedin.com/](https://www.linkedin.com/in/asairi-nava/)).

