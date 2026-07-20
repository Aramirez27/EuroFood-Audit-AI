# 🇪🇺 EU Food Law Compliance AI Agent (Core Architecture)

Este repositorio contiene la arquitectura de instrucciones del **Agente Central de IA** diseñado para actuar como el primer filtro crítico y automatizado en la auditoría de etiquetado de ingredientes bajo la estricta normativa de la Unión Europea. 

A diferencia de un prompt conversacional estándar, este agente opera mediante un flujo lógico basado en **razonamiento y herramientas (Tools)**, procesando datos multilingües crudos e interactuando con bases de datos regulatorias para emitir un diagnóstico determinista en formato **JSON estructurado**.

---

## 🏗️ Arquitectura del Sistema

El agente está diseñado para acoplarse a un entorno de desarrollo (ej. LangChain, CrewAI, Autogen o desarrollo nativo de APIs) ejecutando el siguiente flujo de trabajo:

1. **Ingestión:** Recibe texto directo o cadenas limpias provenientes de un módulo externo de OCR multilingüe (con soporte para los 24 idiomas oficiales de la UE).
2. **Validación Cruzada (Tools):** Invoca herramientas específicas de código para contrastar los aditivos declarados con los registros de la EFSA y validar los 14 alérgenos obligatorios (Anexo II del Reg. 1169/2011).
3. **Triaje de Riesgo:** Aplica una matriz de evaluación adaptada a los estándares de auditoría del **Reglamento (UE) 2024/1689 (AI Act)** para mitigar sesgos en la clasificación de alertas.
4. **Output Interoperable:** Devuelve un esquema JSON limpio listo para ser consumido por un Dashboard web o interfaz gráfica utilizada por el auditor humano.

---

## 🔧 Estructura de Integración del Agente

Para integrar este agente en tu stack técnico, utiliza las directrices definidas en el archivo del prompt del sistema. El agente requiere que expongas en el entorno de ejecución las siguientes funciones (`Tools`):

*   `check_efsa_additives_db(ingredientes_lista)`: Consulta programática a la base de datos local/remota de aditivos prohibidos o restringidos por la EFSA (ej. E-171).
*   `validate_eu_allergens_and_lexicon(texto_extraido, pais_comercializacion)`: Mapeo lingüístico automatizado de los 14 alérgenos y verificación del cumplimiento idiomático del mercado destino (Art. 15 del Reg. 1169/2011).

---

## 📜 El System Prompt del Agente

