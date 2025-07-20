# UI Evaluation and Usability Report

## 1. Heuristic Evaluation, Usability & Accessibility Criteria
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
| Aesthetic and Minimalist design | Jerarquía visual limpia, sin información superflua.                                        |
| Help Users Recognize, Diagnose and Recover from Errors | Mensajes de error claros y útiles.                    |
| **Accessibility**         | Contraste WCAG ≥4.5:1, tamaño de fuente ≥16sp, áreas táctiles ≥48dp.                              |

---

## 2. Screen-by-Screen Scorecard

| Screen        | Visual Hierarchy (score) | Consistency (score) | Learnability (score) | Accessibility (score) | Improvements Needed         |
|---------------|--------------------------|---------------------|----------------------|-----------------------|-----------------------------|
| **Dashboard** | 4/5                      | 5/5                 | 4/5                  | 3/5                   | Mejorar contraste de tarjetas |
| **Add Expense**| 5/5                     | 5/5                 | 5/5                  | 4/5                   | —                           |
| **History**   | 4/5                      | 4/5                 | 4/5                  | 3/5                   | Mayor distinción visual de filas |

---

## 3. Detailed Usability Findings & improvements

- **Visual Hierarchy** (score: 4/5)  
  - Balance y presupuesto resaltan; el FAB podría usar un color más intenso.  
  - **improvement:** Ajustar la paleta para aumentar el contraste de los cards.  

- **Consistency** (score: 5/5)  
  - Tipografía, iconografía y espaciados uniformes en todas las pantallas.  
  - **improvement:** Ninguna acción inmediata requerida.  

- **Learnability & Flow** (score: 4/5)  
  - Flujo Dashboard → Add → History intuitivo.  
  - **improvement:** Agregar micro-interacciones (p.ej., confirmación visual al guardar).  

- **Accessibility** (score: 3/5)  
  - Texto secundario (<16sp) y contraste de elementos crítico bajo WCAG.  
  - **improvement:** Aumentar tamaño de texto secundario y reforzar contraste según WCAG AA.  

- **Error Prevention** (score: 5/5)  
  - Acciones de borrado requieren confirmación; evita pérdidas accidentales.  
  - **improvement:** Añadir mensajes inline para campos del formulario.

---

## 4. Overall Usability & Accessibility Evaluation

La **usability** general (promedio score: 4.2/5) es alta gracias a la consistencia y claridad de la interfaz.  
Sin embargo, la **accessibility** (promedio score: 3.3/5) necesita mejoras en contraste y tamaños de fuente para cumplir los estándares de **accessibility**.

---

## 5. recommendations & Next Steps

1. **Increase Contrast**  
   - Aumentar el contraste de cards y FAB para alcanzar WCAG 2.1 AA.  
   - **improvement:** Actualizar color primario y secundario en el sistema de diseño.

2. **Enhance Touch Targets**  
   - Verificar que todos los botones y elementos interactivos sean ≥48dp.  
   - **improvement:** Revisar componentes y ajustar padding o margin.

3. **Augment Visual Distinction**  
   - Alternar fondos de fila o insertar separadores en History para mejorar legibilidad.  
   - **improvement:** Implementar “zebra stripes” o divider components.

4. **Provide Contextual Help**  
   - Agregar tooltips o helper texts en campos del formulario.  
   - **improvement:** Incluir textos breves bajo cada TextField.

5. **Conduct User Testing**  
   - Planificar sesiones de usabilidad para validar flujo y accesibilidad.  
   - **improvement:** Recoger feedback de usuarios reales y ajustar iterativamente.

