# UI Evaluation and Usability Report

## 1. Heuristic Evaluation Criteria
Se aplicaron las 10 heurísticas de Nielsen para evaluar la **usability** de los mockups v3.

| Criterio               | Descripción                                                                                          |
|------------------------|------------------------------------------------------------------------------------------------------|
| Visibility of System Status | El usuario siempre sabe qué está pasando (carga de datos, envío de formulario).               |
| Match Between System and Real World | Terminología familiar y metáforas visuales reconocibles.                                |
| User Control and Freedom | Acciones deshacer/rehacer y navegación clara.                                                     |
| Consistency and Standards | Uniformidad en tipografía, colores e iconografía.                                                 |
| Error Prevention       | Diseño que evita errores de usuario (e.g., confirmaciones antes de borrar).                          |
| Recognition Rather Than Recall | Elementos y acciones visibles sin memorizar flujos.                                         |
| Flexibility and Efficiency of Use | Atajos (swipe-to-delete, FAB) para usuarios avanzados.                                |
| Aesthetic and Minimalist Design | Jerarquía visual clara, sin información irrelevante.                                       |
| Help Users Recognize, Diagnose and Recover from Errors | Mensajes de error claros y accesibles.                        |
| **Accessibility** (added) | Contraste WCAG, tamaño de fuente ≥16sp, áreas táctiles ≥48dp.                                   |

## 2. Screen-by-Screen Usability Evaluation

| Screen           | Visual Hierarchy | Consistency | Learnability | Accessibility | Notes                                                   |
|------------------|------------------|-------------|--------------|---------------|---------------------------------------------------------|
| Dashboard        | 4/5              | 5/5         | 4/5          | 3/5           | FAB destacada; mejorar contraste en tarjetas.           |
| Add Expense      | 5/5              | 5/5         | 5/5          | 4/5           | Formulario claro; etiquetas legibles; buen contraste.   |
| History          | 4/5              | 4/5         | 4/5          | 3/5           | Agrupación por fecha útil; filas necesitan más contraste.|

## 3. Detailed Notes and Accessibility Findings

- **Contrast**: Algunas tarjetas presentan bajo contraste; ajustar colores para cumplir WCAG 2.1 AA.  
- **Font Sizes**: El texto secundario (fechas, estados) cae por debajo de 16sp.  
- **Touch Targets**: Verificar que todos los botones e íconos tengan al menos 48dp.  
- **Error Prevention**: Añadir confirmación al eliminar tareas desde History.  

## 4. Overall Usability and UX Evaluation

La **usability** general es alta gracias a la claridad del flujo y la consistencia visual.  
Sin embargo, es necesario reforzar aspectos de **accessibility** y contraste.  

## 5. Recommendations

1. **Aumentar contraste** de tarjetas y FAB.  
2. **Incrementar tamaño** de texto secundario y botones.  
3. **Añadir ayudas contextuales** (tooltips, mensajes inline).  
4. **Realizar pruebas de usuario** para validar flujo y detectar puntos de confusión.  

---  
_End of UI Evaluation Report_  
