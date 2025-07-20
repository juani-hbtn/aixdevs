# UI Evaluation and Usability Report

## 1. Heuristic Evaluation and Usability Criteria
En esta **evaluation** aplicamos los principios de **heuristics** de Nielsen para valorar la **usability** de las pantallas v3 y comprobar la **accessibility**.

| Criterion               | Description                                                                                          |
|-------------------------|------------------------------------------------------------------------------------------------------|
| Visibility of System Status | El usuario siempre sabe qué está pasando (carga, envío).                                        |
| Match Between System and Real World | Terminología familiar y metáforas visuales claras.                               |
| User Control and Freedom | Navegación clara y acciones de deshacer/rehacer intuitivas.                                         |
| Consistency and Standards | Uniformidad en tipografía, colores e iconografía.                                                 |
| Error Prevention         | Diseño que evita errores críticos (ej. confirmación al borrar).                                     |
| Recognition Rather Than Recall | Elementos visibles que reducen la carga de memoria.                                          |
| Flexibility and Efficiency of Use | Atajos como swipe-to-delete y FAB para usuarios avanzados.                              |
| Aesthetic and Minimalist Design | Jerarquía visual limpia, sin información superflua.                                        |
| Help Users Recognize, Diagnose and Recover from Errors | Mensajes de error claros y útiles.                    |
| **Accessibility**         | Contraste WCAG ≥4.5:1, tamaño de fuente ≥16sp, áreas táctiles ≥48dp.                              |

---

## 2. Screen-by-Screen Usability Evaluation

| Screen           | Visual Hierarchy | Consistency | Learnability | Accessibility | Notes                                                   |
|------------------|------------------|-------------|--------------|---------------|---------------------------------------------------------|
| **Dashboard**    | 4/5              | 5/5         | 4/5          | 3/5           | FAB destacada; mejorar contraste de tarjetas.           |
| **Add Expense**  | 5/5              | 5/5         | 5/5          | 4/5           | Formulario claro; buen contraste en campos y botones.   |
| **History**      | 4/5              | 4/5         | 4/5          | 3/5           | Agrupación por fecha útil; filas necesitan más contraste.|

---

## 3. Detailed Usability Findings

- **Visual Hierarchy:**  
  - Balance y presupuesto resaltan; FAB necesita color más fuerte.  
- **Consistency:**  
  - Tipografía e iconografía uniformes, mejora en v3 con bottom nav.  
- **Learnability & Flow:**  
  - Flujo Dashboard → Add → History es muy intuitivo.  
- **Accessibility:**  
  - Texto secundario (<16sp) y contraste de tarjetas deben ajustarse.  
- **Error Prevention:**  
  - Incluir confirmación al eliminar desde History reduce errores.

---

## 4. Overall Usability and Accessibility Evaluation

La **usability** general es alta gracias a la claridad y consistencia visual.  
No obstante, se requiere reforzar la **accessibility** ajustando contraste y tamaños para cumplir heuristics de accesibilidad.

---

## 5. Recommendations and Next Steps

1. **Incrementar contraste** en tarjetas y FAB para cumplir WCAG.  
2. **Aumentar tamaño de texto** secundario y controles táctiles (≥48dp).  
3. **Añadir ayuda contextual** (tooltips, mensajes inline).  
4. **Realizar pruebas de usuario** focalizadas en accesibilidad y navegación.

