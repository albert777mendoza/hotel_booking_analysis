# Hotel Booking Analysis — Análisis Estratégico de Revenue y Cancelaciones

### 📌 Ficha Ejecutiva

- **Problema de negocio:** Identificar los patrones de cancelación, el perfil de cliente de mayor riesgo y las oportunidades de optimización de revenue en dos hoteles portugueses para reducir pérdidas económicas y mejorar la rentabilidad.
- **Dataset utilizado:** 119,390 reservas reales de dos hoteles portugueses (City Hotel en Lisboa y Resort Hotel en el Algarve) durante el período 2015–2017, con información de cancelaciones, tarifas, segmentos de mercado y perfil de clientes.
- **Herramientas:** Python, Pandas, Seaborn, Matplotlib, SQL, SQLAlchemy.
- **Resultados principales:**
  * El 37% de todas las reservas fueron canceladas en el período analizado, con una brecha significativa entre el City Hotel (41.7%) y el Resort Hotel (27.8%).
  * El perfil de cliente de mayor riesgo es un viajero Transient que reserva por Online TA con más de 90 días de anticipación, sin depósito y con historial de cancelaciones previas (94% reincidencia).
  * El 53.7% de las cancelaciones se concentran en temporada alta (Agosto, Julio, Mayo, Junio, Abril), precisamente cuando el ADR es el más alto del año (€125.17/noche).
  * Online TA es el segmento más valioso (€13.7M en revenue generado) y simultáneamente el más riesgoso por su alta tasa de cancelación.
- **Impacto potencial de negocio:**
  * El revenue total perdido por cancelaciones en el período 2015–2017 asciende a **€16,721,837**, con el City Hotel concentrando el 65.1% de esas pérdidas (€10.8M).
  * Reducir la tasa de cancelación del City Hotel del 41.7% al 30% representaría recuperar aproximadamente **€3.2M en revenue** con políticas comerciales bien dirigidas.
  * La identificación del perfil de riesgo permite al hotel intervenir en el momento de la reserva antes de que la cancelación ocurra.
- **Recomendación final:** Implementar políticas de depósito obligatorio para reservas Transient con más de 90 días de anticipación, activar estrategias de retención en temporada alta e incentivar la reserva directa para reducir la dependencia de intermediarios.

[📓 Notebook](https://github.com/albert777mendoza/hotel_booking_analysis/blob/main/notebooks/hotel_analysis.ipynb) | [📊 Dashboard](https://github.com/albert777mendoza/hotel_booking_analysis/blob/main/dashboard/hotel-dashboard.html)

---

### Objetivo

Proyecto de análisis estratégico orientado a identificar los patrones de cancelación y las oportunidades de optimización de revenue en dos hoteles portugueses. El análisis permite construir el perfil del cliente de alto riesgo de cancelación y cuantificar el impacto económico para apoyar decisiones comerciales con base en datos.

---

### Herramientas y tecnologías

Python | Pandas | Seaborn | Matplotlib | SQL | SQLAlchemy |

---

### Procesos desarrollados

Limpieza de datos | Transformación de datos |
Análisis Exploratorio de Datos (EDA) |
Análisis de cancelaciones | Segmentación de clientes por riesgo |
Análisis de revenue (ADR, RevPAR) | Consultas SQL sobre base de datos relacional |

---

### Preguntas clave

- ¿Quién cancela? — ¿qué perfil de cliente (tipo, segmento, canal) tiene mayor probabilidad de cancelar?
- ¿Cuándo cancela? — ¿cómo influye la anticipación de la reserva en la tasa de cancelación?
- ¿Cuánto cuesta? — ¿cuál es el impacto económico real de las cancelaciones por hotel, temporada y segmento?
- ¿Dónde está el revenue? — ¿qué segmentos y temporadas generan mayor valor y mayor riesgo simultáneamente?

---

### Metodología

- **Preprocesamiento de datos:** limpieza de nulos, corrección de tipos de datos, filtrado de outliers en ADR (valores negativos y extremos como €5,400/noche) y creación de variables derivadas como temporada, lead time segmentado y métricas de revenue.
- **Análisis Exploratorio de Datos (EDA):** exploración de la evolución de reservas 2015–2017, distribución de cancelaciones por tipo de cliente, segmento de mercado, canal de distribución y anticipación de reserva. Identificación de patrones estacionales recurrentes.
- **Análisis de cancelaciones:** construcción del perfil de cliente de alto riesgo mediante el cruce de variables: tipo de cliente, canal de origen, lead time, tipo de depósito e historial de cancelaciones previas. Validación de la relación directamente proporcional entre anticipación y tasa de cancelación.
- **Revenue Analysis:** cálculo de ADR y RevPAR por hotel, temporada y segmento de mercado. Cuantificación del revenue perdido por cancelaciones a nivel de país, segmento y mes. Identificación de la concentración de pérdidas en temporada alta.
- **Análisis SQL:** consultas sobre base de datos relacional para responder preguntas de negocio clave y validar los hallazgos obtenidos en Python.
- **Conclusiones y recomendaciones:** ficha ejecutiva con el perfil de riesgo, el impacto económico estimado y un plan de acción priorizado para la gerencia hotelera.

---

### Visualizaciones destacadas

Indicadores clave del análisis: tasa de cancelación global, revenue perdido total y ADR promedio por hotel. Resumen ejecutivo del impacto económico del período 2015–2017.

![Indicadores clave](images/indicadores_clave.png)

Tasa de cancelación por hotel. El City Hotel (41.7%) presenta una brecha significativa frente al Resort Hotel (27.8%), lo que concentra las acciones prioritarias de retención en el perfil urbano.

![Cancelación por hotel](images/cancelacion_hotel.png)

Relación entre anticipación de reserva (lead time) y tasa de cancelación. Las reservas con más de 181 días de anticipación alcanzan el 57% de cancelación, confirmando una relación directamente proporcional entre el tiempo de antelación y el riesgo.

![Cancelación por anticipación](images/anticipacion_cancelacion.png)

Revenue perdido por cancelaciones acumulado en el período 2015–2017. El City Hotel concentra el 65.1% de las pérdidas (€10.8M), lo que define la prioridad de intervención por tipo de hotel.

![Revenue perdido](images/revenue_perdido.png)

Tasa de cancelación por canal de distribución. Los intermediarios digitales (TA/TO) generan consistentemente más cancelaciones que los canales directos, validando la estrategia de incentivos para reserva directa.

![Cancelación por canal](images/cancelacion_canal.png)

---

### Conclusiones y recomendaciones

- El 37% de cancelaciones global representa una pérdida de €16.7M en el período analizado, con el City Hotel concentrando el 65.1% del impacto económico.
- El perfil de mayor riesgo es claro y accionable: cliente Transient, canal Online TA, más de 90 días de anticipación, sin depósito y con historial de cancelaciones previas (94% reincidencia).
- La concentración de cancelaciones en temporada alta (53.7% en Agosto, Julio, Mayo, Junio y Abril) agrava el impacto porque coincide con los meses de ADR más alto — cada cancelación en verano vale casi el doble que una en enero.
- Online TA es el segmento más complejo: genera el mayor revenue real (€13.7M) pero también la mayor pérdida por cancelaciones, requiriendo estrategias específicas de retención, no de exclusión.

### Recomendaciones

- Implementar **depósito obligatorio no reembolsable** para reservas Transient con más de 90 días de anticipación y sin historial limpio, activando esta política de forma diferenciada por perfil de riesgo.
- Activar **comunicación proactiva en temporada alta** (Julio y Agosto) con ofertas de upgrade, beneficios exclusivos y recordatorios para reducir cancelaciones en los meses de mayor ADR.
- Desarrollar **incentivos para reserva directa** — menor comisión, mayor control y menor tasa de cancelación — para reducir la dependencia de intermediarios como Booking y Expedia.
- Implementar un **sistema de alertas por reincidencia** que identifique automáticamente clientes con cancelaciones previas y aplique políticas más estrictas desde el momento de la reserva.
