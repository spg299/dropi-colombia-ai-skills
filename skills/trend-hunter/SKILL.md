---
name: trend-hunter
description: "Identifica tendencias emergentes y oportunidades de productos para dropshipping COD en Colombia con Dropi. Úsalo cuando busques productos ganadores, validar demanda, analizar Google Trends o detectar nichos en alza."
type: workflow
lifecycle: active
---

# Trend Hunter — Detección de Tendencias para Dropshipping Dropi Colombia

Identifica y prioriza tendencias de búsqueda, productos y nichos con potencial de utilidad neta sostenible en el mercado colombiano de dropshipping COD (contra entrega) vía Dropi. Nunca inventes datos de volumen o interés; usa solo fuentes verificables.

## Workflow Principal

1. **Definir alcance**
   - País: Colombia (geo: CO). Idioma: español.
   - Horizonte: 12 meses, énfasis en últimos 90 días y proyección estacional.
   - Filtros obligatorios: productos físicos aptos para COD, peso/volumen razonable, proveedores locales Dropi potenciales, margen potencial >30% neto estimado (sin inventar cifras).

2. **Recolectar señales**
   - Google Trends (web o browser): interés relativo, consultas en aumento, temas relacionados, comparación de keywords.
   - Señales secundarias (si disponibles): redes sociales, marketplaces locales, reportes públicos.
   - Categorías prioritarias Dropi: belleza, hogar, salud/bienestar, moda, gadgets, mascotas, bebé.

3. **Analizar y puntuar**
   - Velocidad de crecimiento (rising queries).
   - Estacionalidad vs. evergreen.
   - Competencia relativa (volumen de anunciantes o saturación visible).
   - Alineación con COD y logística Colombia (entrega 24-72h típica).

4. **Priorizar y reportar**
   - Ranking de 5-10 oportunidades.
   - Para cada una: keyword principal, interés relativo (solo si obtenido de fuente), señales de alza, riesgos, recomendaciones de validación posterior.
   - Salida estructurada (markdown + JSON opcional).

5. **Entregar y recomendar siguiente paso**
   - Pasar top candidatos a `winning-product-hunter` o `consumer-psychology`.
   - Actualizar `business-learning-memory` con patrones detectados.

## Metodologías Profesionales

- **Google Trends Analysis**: Interés relativo (0-100), rising queries (+X%), related topics/queries, geo CO, timeframe 12m / 90d / 30d.
- **Trend Velocity Score** (simple): Combinar crecimiento reciente + volumen relativo + estabilidad. No calcular volúmenes absolutos inventados.
- **Filtro COD/Dropi**: Productos de bajo riesgo de devolución (no ropa de talla compleja, no frágiles extremos), precio de venta típico 60k-200k COP.
- **Estacionalidad**: Detectar picos (Navidad, Día de la Madre, Black Friday, etc.) vs. demanda base.

## Herramientas y Conectores

- `web_search` y `browser_execute` para Google Trends y fuentes públicas.
- Python (`pandas`) solo si se necesita procesar series de datos exportadas.
- Google Drive/Sheets (si conectado) para guardar reportes históricos.
- Modelos externos (Gemini/ChatGPT/Qwen) para síntesis de insights cualitativos, nunca como fuente numérica.
- Evitar dependencias de pago; priorizar acceso gratuito a Trends.

## Datos de Entrada y Salida

**Entrada**:
- Keywords o categorías (ej. "productos para el hogar Colombia", "tendencias belleza 2026").
- Filtros opcionales: rango de precio, categoría Dropi, estacionalidad.

**Salida**:
- Reporte estructurado:
  - Top tendencias rankeadas.
  - Por cada una: keyword, tipo (rising/evergreen/seasonal), señales de evidencia, score de prioridad (1-10), riesgos, next actions.
  - JSON schema recomendado para integración.

## Indicadores de Rendimiento

- Número de tendencias con evidencia real (no inventadas) por reporte.
- Tasa de conversión a productos validados por `winning-product-hunter`.
- Precisión de priorización (retroalimentación desde memoria o resultados reales).

## Reglas de Decisión

- Priorizar tendencias con crecimiento sostenido >30 días y alineadas con categorías Dropi fuertes.
- Descartar si saturación extrema visible o incompatibilidad con COD (alto riesgo de devolución).
- Si no hay datos de Trends, reportar explícitamente "sin datos verificables" y no inventar.
- Siempre recomendar validación con datos de Dropi o competencia antes de ofertar.

## Restricciones y Protocolos de Seguridad

- Nunca inventar volúmenes de búsqueda, porcentajes de crecimiento o utilidades.
- Distinguir claramente datos observados vs. estimaciones cualitativas.
- No recomendar gasto en ads ni publicación de campañas.
- No almacenar datos personales. Solo tendencias agregadas.
- Verificar fuentes; citar o indicar origen de cada señal.

## Casos de Prueba (resumen)

Ver `evals/evals.json` para detalles. Ejemplos: búsqueda de tendencias de belleza, análisis de nicho hogar, validación de keyword específica.

## Integración con Otras Skills

- **winning-product-hunter**: Recibe top keywords/nichos para búsqueda de productos concretos en Dropi.
- **consumer-psychology**: Pasa insights de motivación de tendencia para copy y ofertas.
- **competitor-intelligence**: Comparte tendencias para análisis de saturación.
- **business-learning-memory**: Almacena patrones de tendencias exitosas o fallidas.
- **profit-calculator**: Solo después de identificar producto concreto.

## Knowledge Graph / Referencias

No hay referencias externas por ahora. Para series de datos complejas, exportar y procesar con Python localmente.
