# Tlecom
Analisis de empresa de telecomunicación


 Análisis de Comportamiento de Clientes en ConnectaTel 
 
 Objetivo del proyectoEl objetivo de este proyecto es analizar el comportamiento de uso real de los servicios móviles (llamadas y mensajes) de los clientes de ConnectaTel en Latinoamérica (México y Colombia). A través del procesamiento, limpieza, análisis estadístico y segmentación de datos, el estudio busca:Identificar patrones de consumo según variables demográficas (edad) y volumen de uso.Detectar valores atípicos (outliers) que representan comportamientos inusuales o clientes de alto valor (heavy users).Generar insights ejecutivos y recomendaciones comerciales orientadas a optimizar la oferta de planes y mejorar la retención de usuarios.
 
 Datasets utilizados
 El análisis integra tres fuentes principales de datos correspondientes a registros hasta el año 2024:plans.csv: Catálogo con la información de beneficios y tarifas de los planes comerciales (Basico y Premium).users_latam.csv: Información demográfica y contractual de los usuarios (ID, edad, ciudad, fecha de registro, plan asignado y fecha de cancelación/churn).usage.csv: Detalle transaccional del uso de red (tipo de interacción: llamada o mensaje, duración en minutos o longitud del texto y fecha).
 
 Etapas del análisis realizadasCarga y Exploración Inicial: 
 Inspección de la estructura de las tablas, validación de tipos de datos (.info()) y dimensiones de los datasets (.shape).Identificación y Limpieza de Calidad de Datos:Tratamiento de Sentinels: Imputación de valores sentinels en la edad (-999) utilizando la mediana de edades válidas (48 años).

Manejo de Nulos y Faltantes: Estandarización de ausencias geográficas en city (? y nulos) como información no disponible, y eliminación de registros de uso sin fecha.Estandarización Temporal: Conversión de fechas a tipo datetime y filtrado/tratamiento de años inconsistentes fuera del rango del estudio (fechas en 2026).

Estadística Descriptiva e Integración: Unificación de los datos de actividad por cliente (user_profile) para medir totales de llamadas, minutos y mensajes.

Detección de Outliers (Método IQR): Cálculo de cuartiles ($Q_1$, $Q_3$) e $IQR$ para determinar límites teóricos de consumo e identificar visualmente a los clientes atípicos mediante boxplots.

 Segmentación de Clientes:
 
 Por Uso: Clasificación lógica en Bajo uso, Uso medio y Alto uso.
 Por Edad: Categorización directa mediante .loc en Jóvenes (<35), Adultos (35-60) y Mayores (>60).Visualización e Insights Ejecutivos: Generación de gráficos (countplot, boxplot) y redacción de conclusiones estratégicas para la toma de decisiones del negocio.
