# Product Idea: FamilyTask AI

## Visión del Producto
FamilyTask AI es una aplicación web y móvil que facilita la organización de tareas y responsabilidades compartidas dentro de familias o grupos de convivencia, apoyándose en recordatorios inteligentes impulsados por AI. Con pocas configuraciones, cualquier miembro puede asignar, priorizar y recibir notificaciones automáticas basadas en hábitos y disponibilidad de cada usuario.

## Tipos de Usuario y Casos de Uso

1. **Padre/Madre Coordinador(a)**  
   - Asigna tareas domésticas (compras, limpieza) a diferentes miembros.  
   - Recibe recordatorios automáticos antes de cada actividad.  
2. **Hijo(a) Adolescente**  
   - Consulta su lista de responsabilidades diarias (deberes, cuidado de mascotas).  
   - Marca tareas como completadas y recibe elogios virtuales.  
3. **Roommate Independiente**  
   - Gestiona facturas compartidas (luz, agua, internet).  
   - Programa avisos de pago basados en fechas de vencimiento.  
4. **Cuidador(a) Sénior**  
   - Planifica y recuerda eventos médicos o citas.  
   - Puede delegar notificaciones a miembros más jóvenes.  
5. **Invitado/Ocasional**  
   - Accede a tareas puntuales (regar plantas, alimentar mascotas) sin necesidad de registro profundo.  
   - Recibe un enlace temporal y sólo ve lo necesario.

## Características Clave y Diferenciadores

- **Recordatorios Inteligentes**: El motor de AI agrupa y reprograma tareas según la carga de trabajo y hábitos de los usuarios.  
- **Asignaciones Flexibles**: Permite reasignar tareas en un clic y redistribuir automáticamente si alguien está sobrecargado.  
- **Gamificación Ligera**: Puntos y badges para motivar el cumplimiento, con ranking familiar opcional.  
- **Enlaces de Invitado**: Usuarios ocasionales pueden unirse con un enlace QR sin necesidad de crear cuenta.  
- **Integraciones**: Con calendarios (Google, Outlook) y asistentes de voz (Alexa, Google Assistant) para notificaciones habladas.

## Restricciones y Requisitos

- **Plataforma**: Web React + Responsive; apps nativas iOS/Android (opcional fase 2).  
- **Autenticación**: Opción de Single Sign-On (familia) o enlaces de invitado sin login.  
- **Persistencia**: Base de datos en la nube (Firebase o AWS DynamoDB).  
- **Privacidad**: Datos cifrados end-to-end; control granular de permisos por tarea.  
- **Offline-First**: Sincronización automática al reconectar para accesos esporádicos.

