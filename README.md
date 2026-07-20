# 🇪🇺 EuroFood-Audit-AI (Core Architecture)

Filtro previo inteligente basado en IA para la auditoría de etiquetado alimentario en la Unión Europea. Soporta ingestión de OCR multilingüe (24 idiomas), validación mediante herramientas de la EFSA y matriz de riesgo de 4 niveles conforme al Reg. (UE) 2024/1689.

---

## 🏗️ Arquitectura del Sistema

El agente está diseñado para acoplarse a un entorno de desarrollo (ej. LangChain, CrewAI o desarrollo nativo) ejecutando el siguiente flujo de trabajo:

1. **Ingestión:** Recibe texto directo o cadenas limpias de un módulo de OCR multilingüe.
2. **Validación Cruzada (Tools):** Invoca herramientas de código para contrastar aditivos con registros de la EFSA y validar los 14 alérgenos obligatorios (Reg. 1169/2011).
3. **Triaje de Riesgo:** Aplica una matriz de evaluación adaptada a los estándares del **Reglamento (UE) 2024/1689 (AI Act)**.
4. **Output Interoperable:** Devuelve un esquema JSON limpio para el Dashboard del auditor humano.

---

## 🚀 Configuración del Agente

Las instrucciones maestras de comportamiento, restricciones, herramientas requeridas y el esquema JSON estricto de salida se encuentran modularizados en su propio archivo dentro del repositorio:

👉 **[Acceder al System Prompt del Agente](./core/agent_system_prompt.md)**

---

## ⚖️ Exención de Responsabilidad / Legal Disclaimer

Este sistema de agentes de IA actúa exclusivamente como una herramienta de triaje previo y asistencia técnica. Conforme al Reglamento (UE) 2024/1689 (Ley de IA), este sistema requiere obligatoriamente la validación y revisión final de un **auditor humano cualificado** antes de aprobar cualquier etiqueta. El uso de este software es bajo su propio riesgo; los autores no se responsabilizan de sanciones o alertas RASFF.
