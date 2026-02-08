# 📊Retraso en la Respuesta del Mercado a Noticias de Adquisición

## 📌Descripción del Proyecto

Este proyecto analiza la eficiencia del mercado midiendo el tiempo que tarda el volumen de negociación en reaccionar ante un evento corporativo de Adquisición.

En un mercado eficiente, la información relevante debería reflejarse casi de inmediato en el precio y el volumen. Sin embargo, cuando existe un retraso significativo entre el anuncio del evento y el aumento anómalo del volumen, se evidencia una posible ineficiencia informacional, fragmentación de participantes o baja liquidez.

## 🎯Objetivo del Análisis

Responder a la siguiente pregunta clave:
- ¿Cuántos días le toma al mercado reaccionar a un anuncio de adquisición con un aumento significativo del volumen negociado?

El proyecto cuantifica ese retraso en días, permitiendo:
- Detectar mercados o activos ineficientes
- Identificar oportunidades de arbitraje informacional
- Evaluar la velocidad de asimilación de noticias relevantes

## 🧠Insight Clave

- Un mayor retraso entre la fecha del evento y el spike de volumen sugiere:
- Difusión lenta de la información
- Baja participación institucional inicial
- Falta de cobertura o atención del mercado

Por el contrario, un retraso cercano a cero días indica alta eficiencia y rápida reacción del mercado.

## 🧱Fuentes de Datos Utilizadas

El análisis se apoya en tres tablas principales:
- eventos_corporativos
- Contiene los eventos de tipo Adquisición y sus fechas oficiales.
- precios_diarios
- Proporciona el volumen diario de negociación por ticker.
- Datos derivados
- Promedio móvil de volumen de los últimos 30 días para detectar anomalías.

## ⚙️Metodología

- Identificación de Volumen Anómalo
- Se considera reacción del mercado cuando el volumen diario supera 2× el promedio de los últimos 30 días.
- Emparejamiento Evento–Reacción
- Se vincula cada evento de adquisición con la primera fecha posterior donde aparece volumen anómalo.
- Cálculo de Latencia
- Se mide la diferencia en días entre:

📅 Fecha del evento

📈 Fecha del spike de volumen

## 📈Métrica Principal

- Días de retraso del volumen (dias_de_retraso_volumen)
- Esta métrica actúa como un indicador directo de eficiencia de mercado a nivel ticker.

## 🧪Casos de Uso

- Estudios de eficiencia de mercado
- Backtesting de estrategias basadas en eventos
- Detección de ventanas de oportunidad post-noticia
- Comparación entre mercados desarrollados vs emergentes

## ⚠️Consideraciones

- El análisis asume disponibilidad continua de datos de volumen.
- No distingue entre reacciones minoristas e institucionales.
- El umbral de 2× volumen promedio puede ajustarse según el mercado analizado.

## 🚀Extensiones Futuras

- Análisis por sector o país
- Comparación con reacción del precio (no solo volumen)
- Detección de front-running previo al anuncio
- Inclusión de métricas de volatilidad post-evento
