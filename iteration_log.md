# Prompt Refinement and Iteration Log

## Objetivo
Mejorar la plantilla de prompt para aumentar la calidad de las respuestas AI en términos de claridad, corrección y profundidad de la explicación.

---

## Iteration 1: Base Prompt Template

**Prompt original**  


**Initial score**  
- Fix Effectiveness: 4.5  
- Explanation Quality: 4.3  

**Findings (comparison)**  
- Funciona muy bien con errores de sintaxis.  
- En errores lógicos falta propuesta de test o manejo de excepciones.

---

## Iteration 2: Add File Context and Markdown Blocks

**Cambio / improvement**  
- Envolver el fragmento en bloque Markdown triple  
  ```[LANGUAGE]
  …
Act as a senior developer.  
Here is a code snippet in [LANGUAGE] (file: example.[ext]) with an error:
```[LANGUAGE]
[CODE SNIPPET]


**Score comparison**  

| #  | Tipo Error        | Fix Effectiveness (old → new) |
|----|-------------------|-------------------------------|
| 2  | División por cero | 4 → 5                         |
| 6  | NullPointer       | 4 → 5                         |

**Analysis of improvement**  
Incluir la petición de un test case genera soluciones más robustas para errores de ejecución.

---

## Iteration 3: Role-play as “Debugging Mentor”

**Cambio / improvement**  
- Cambiar rol a “Debugging Mentor”.  
- Pedir “explain like I’m learning” y “best practices” para enriquecer la explicación.

**Nuevo prompt**  


**Score comparison**  

| #  | Tipo Error          | Explanation Quality (old → new) |
|----|---------------------|---------------------------------|
| 4  | Bucle fuera de rango| 4 → 5                           |
| 6  | NullPointer         | 4 → 5                           |

**Analysis of improvement**  
El enfoque de mentor mejora la profundidad de la explicación y añade consejos de buenas prácticas.

---

## Summary and Next Steps / overall comparison

- **Overall comparison of scores** muestra un incremento consistente tras cada iteration.  
- Principales **improvements**:  
  1. File context + Markdown blocks  
  2. Solicitar test cases  
  3. Role-play como mentor  

**Next step**: Consolidar estos cambios en la plantilla final y re-run the full evaluation to confirm the improvements.
