________________________________________
📄 Declaración Estratégica y Arquitectura Técnica (Versión Extendida): Portal Universitario Digital 3.0
Resumen Ejecutivo
El Portal Universitario Digital representa el pilar fundamental de la estrategia de Transformación Digital de la institución. Más allá de ser un sitio web, se establecerá como un Ecosistema Unificado de Servicios (EUS), diseñado para centralizar la gestión académica, administrativa y financiera. Su objetivo es migrar del modelo de operación tradicional a un entorno ágil, centrado en la experiencia del usuario (UX) y dirigido por la inteligencia de datos. Este documento detalla la visión estratégica, la arquitectura técnica recomendada y el plan de escalabilidad para asegurar su éxito a largo plazo.
________________________________________
HOJA 1: El Mandato Estratégico, la Visión del Ecosistema y Análisis Inicial
I. Declaración de Rol y Responsabilidad
OMAR CAMPOS  Jefe de Grupo de lideres me toco llevar la coordinación de gerencia,jefe de diseño sistemas y otros departamentos  en esta fase inicial de código abierto (Open Source), mi responsabilidad ha sido liderar la concepción del prototipo (V0.9 - Beta) y definir la Visión Estratégica del proyecto a gran escala. Esta visión abarca la integración de los servicios académicos, la arquitectura técnica necesaria para una escalabilidad infinita y la elaboración de la hoja de ruta para la implementación de la versión 3.0 (Producción).
II. Visión Estratégica: De Plataforma a Ecosistema de Valor
El Portal Digital 3.0 tiene un triple mandato estratégico que aborda los desafíos críticos de la educación superior moderna:
A. Democratización y Acceso 24/7
El portal debe ser la herramienta principal para eliminar las barreras geográficas y temporales, garantizando que la información y los servicios críticos estén disponibles las 24 horas del día, los 7 días de la semana. Esto soporta directamente las modalidades de estudio híbridas (Blended Learning) y a distancia.
B. Empoderamiento del Usuario y Eficiencia
Se busca dotar a cada actor (estudiante, docente, administrador) de herramientas de autogestión altamente intuitivas. Esto reduce la carga operativa del personal administrativo, liberándolos para enfocarse en tareas de mayor valor estratégico y mejorando la tasa de resolución de consultas.
C. Transparencia Operacional y Trazabilidad
Al centralizar todos los procesos (matrícula, calificaciones, asistencias, logs de actividad), el sistema garantizará una trazabilidad completa y un alto nivel de transparencia. Esto es vital para la rendición de cuentas institucional y para cumplir con los estándares regulatorios.
III. Módulos del Ecosistema Unificado de Servicios (EUS)
Módulo de Servicio	Usuarios Principales	Funcionalidades Clave
Portal Académico (LMS)	Estudiantes, Docentes	Distribución de Tareas/Materiales, e-Learning, Seguimiento de Asistencia, Historial de Notas y Avance Curricular.
Portal de Gestión	Docentes, Administradores	Gestión de Cargas Horarias, Aulas y Asignaciones. Cierre y Validación de Actas de Calificaciones, Solicitudes de Licencia.
Portal de Servicios al Alumno	Estudiantes, Administración	Matrícula y Reinscripción Online, Solicitud de Documentos (Constancias, Créditos), Estado de Cuenta y Pagos.
Portal de Inteligencia (BI)	Alta Dirección, Administración	Dashboards de Deserción (Analítica Predictiva), Indicadores de Rendimiento Docente y Eficiencia Administrativa.
Exportar a Hojas de cálculo
________________________________________
HOJA 2: Análisis FODA y Arquitectura Técnica Recomendada
IV. Análisis FODA (Fortalezas, Oportunidades, Debilidades y Amenazas)
Este análisis se centra en la transición del prototipo a la versión final del sistema productivo.
Fortalezas (Aspectos Internos Positivos)
Fortalezas	Descripción
Modelo Modular Basado en Roles	El diseño inicial ya separa claramente las vistas de Estudiante, Docente y Admin, lo que facilita la implementación de la Arquitectura de Microservicios sin colapsar la lógica.
Usabilidad y UX Moderna	El prototipo utiliza diseño Glassmorphism y es completamente responsive, asegurando una alta satisfacción del usuario (NPS) desde la fase Beta.
Tecnologías Universales	El Front-end está construido en HTML/CSS/JavaScript vanilla, lo que reduce la dependencia de frameworks pesados en la fase inicial y facilita la transición a React/Vue.js.
Código Abierto (Open Source)	Al ser un proyecto Open Source en su origen, se fomenta la colaboración interna entre los equipos de desarrollo y la transparencia del código.
Exportar a Hojas de cálculo
Debilidades (Aspectos Internos a Mejorar)
Debilidades	Descripción
Dependencia de Datos Simulados	El prototipo actual no tiene persistencia de datos (usa variables JS), lo que lo hace inútil en un entorno productivo hasta la conexión a una BBDD real.
Seguridad Inexistente	La autenticación es simulada (sin contraseña) y no hay mecanismos de cifrado ni JWT, representando el riesgo más alto en la fase de escalabilidad.
Monolito de Front-end	Todo el código (Estructura, Estilos, Lógica) reside en un único archivo (portal.html), dificultando la mantenibilidad y la escalabilidad de la base de código.
Carencia de Testing	Ausencia de pruebas unitarias o de integración, lo que aumenta el riesgo de bugs críticos al añadir nuevas funcionalidades.
Exportar a Hojas de cálculo
Oportunidades (Aspectos Externos Favorables)
•	Migración a la Nube: Aprovechar la infraestructura de nube (AWS/Azure) para implementar un modelo de pago por uso y garantizar la escalabilidad elástica en picos de matrícula.
•	Inteligencia Artificial (IA): Integrar chatbots basados en LLMs (Large Language Models) para soporte al alumno y análisis predictivo de la deserción.
•	Adopción Institucional: Alta demanda de la comunidad para digitalizar procesos (trámites, pagos), garantizando una alta tasa de adopción post-lanzamiento.
Amenazas (Riesgos Externos a Mitigar)
•	Ataques Cibernéticos: El riesgo de ataques de phishing o inyección SQL aumenta con la exposición pública del portal, lo que requiere invertir en Seguridad Perimetral (WAF).
•	Resistencia al Cambio: Posible resistencia de docentes o personal administrativo a adoptar las nuevas herramientas de gestión.
•	Regulación de Datos: Necesidad de cumplir con normativas de protección de datos (ej. GDPR o leyes locales) al manejar información personal sensible.
V. Arquitectura de Sistemas: Microservicios y API Gateway
Para garantizar la escalabilidad, la robustez y la independencia de las funcionalidades, el sistema se construirá bajo una Arquitectura de Microservicios desacoplada de la interfaz de usuario.
A. El Stack Tecnológico Recomendado
Capa	Herramienta Clave	Razón Estratégica
Front-end (Presentación)	React.js / Vue.js	Permite crear una Single Page Application (SPA) ágil y rápida, y facilita la modularización del desarrollo en componentes reutilizables.
Back-end (Lógica)	Node.js con Express.js (TypeScript)	Ofrece un entorno de alto rendimiento no bloqueante, ideal para manejar grandes volúmenes de solicitudes asíncronas de la comunidad.
Base de Datos (Transaccional)	PostgreSQL	Preferido para datos críticos y estructurados (Calificaciones, Matrícula) debido a su fuerte integridad de datos y robustez ACID.
Base de Datos (NoSQL/Flexible)	MongoDB	Utilizado para datos semi-estructurados (Avisos, Logs, Material Didáctico), brindando flexibilidad en el desarrollo rápido de nuevos módulos.
Exportar a Hojas de cálculo
________________________________________
HOJA 3: Seguridad, DRP y Plan de Implementación
VI. Seguridad, Respaldo y Continuidad Operacional (DRP)
La protección de datos sensibles es una prioridad. El sistema se diseñará bajo el marco de Seguridad por Diseño (Security by Design).
1.	Autenticación y Autorización: Implementación de Bcrypt para el hashing seguro de contraseñas. Uso estricto del Control de Acceso Basado en Roles (RBAC), donde el AuthService verifica los permisos mediante JWT antes de que el Back-end procese cualquier solicitud.
2.	Infraestructura en la Nube: Despliegue en proveedores de nube líderes (AWS, Azure o Google Cloud) utilizando contenedores (Docker y Kubernetes) para garantizar la escalabilidad horizontal (capacidad de auto-crear instancias en picos de demanda).
3.	Recuperación ante Desastres (DRP): Implementación de respaldos automatizados e incrementales diarios de la base de datos (PostgreSQL), replicación de datos a una zona geográfica distinta y un plan de Recuperación ante Desastres (DRP) con un Tiempo Objetivo de Recuperación (RTO) máximo de 4 horas.
VII. Hoja de Ruta del Proyecto (Roadmap)
El desarrollo se ejecutará con una metodología Ágil (Scrum), con sprints de 2-4 semanas, asegurando la entrega continua de valor.
Fase	Enfoque Principal	Hitos Clave	Duración (Estimada)
Fase 1: Infraestructura y Núcleo	Migración de Arquitectura. Desarrollo del AuthService y el Front-end principal.	V1.0 (MVP) Lanzamiento: Login seguro (JWT) y Perfil Básico (Estudiante/Docente/Admin). Repositorio listo para testing.	4 Meses
Fase 2: Motor Académico	Desarrollo del AcademicService y la integración de datos históricos (Matrícula y Notas).	Módulos de Horarios y Calificaciones en Producción. Sincronización de Datos del Sistema Heredado.	5 Meses
Fase 3: Expansión de Servicios	Implementación del LMS para tareas/materiales y el NotificationService.	Gestión de Tareas (Subida/Calificación). Sistema de Avisos Multi-Canal (Email/App).	4 Meses
Fase 4: Optimización y BI	Desarrollo de Dashboards de BI y Pruebas de Carga/Seguridad.	Dashboards de Analítica Predictiva (ej. Alerta de Deserción). Pruebas de Pentesting y Lanzamiento Oficial de V3.0.	3 Meses
Exportar a Hojas de cálculo
VIII. Criterios de Éxito e Indicadores de Rendimiento (KPIs)
El éxito del proyecto se medirá no solo por el lanzamiento técnico, sino por el impacto real en la comunidad universitaria.
A. KPIs de Rendimiento Técnico
•	Disponibilidad (Uptime): 99.95% (Menos de 4 horas de inactividad anual).
•	Latencia de API: Tiempo promedio de respuesta de las consultas críticas (ej. consulta de notas) debe ser inferior a 200 milisegundos.
•	Escalabilidad de Carga: El sistema debe soportar un pico de 10,000 usuarios concurrentes sin degradación del servicio.
B. KPIs de Impacto Estratégico
•	Tasa de Adopción (Estudiantes): 98% de la población activa usando el portal al menos una vez por semana.
•	Tasa de Digitalización de Trámites: Migración del 85% de los trámites administrativos clave a la plataforma digital.
•	Reducción de Costos Operativos: Disminución del 20% en los costos de papelería y gestión manual de trámites durante el primer año.
El Portal Universitario Digital 3.0 será la herramienta que posicione a la institución a la vanguardia educativa, garantizando una gestión moderna, eficiente y preparada para los retos de la próxima década
AQUÍ TE DEJO EL CODIGO PARA SU USO Y MODIFICACIONES ASI COMO BASE PARA QUE HAGAS LO QUE GUSTES

<title>Fundación MOVAPE/UNICEP - Acceso al Portal</title>  <style>      body {          box-sizing: border-box;          margin: 0;          padding: 0;          font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;          overflow-x: hidden;          background: linear-gradient(135deg, #87CEEB 0%, #6B8E23 100%);          min-height: 100vh;      }     .animated-bg {         position: fixed;         top: 0;         left: 0;         width: 100%;         height: 100%;         z-index: -1;         overflow: hidden;     }
    .sphere {         position: absolute;         border-radius: 50%;         background: linear-gradient(45deg, rgba(255,255,255,0.1), rgba(255,255,255,0.3));         backdrop-filter: blur(10px);         animation: float 6s ease-in-out infinite;     }
    .sphere:nth-child(1) {         width: 80px;         height: 80px;         top: 20%;         left: 10%;         animation-delay: 0s;     }
    .sphere:nth-child(2) {         width: 120px;         height: 120px;         top: 60%;         right: 15%;         animation-delay: 2s;     }
    .sphere:nth-child(3) {         width: 60px;         height: 60px;         top: 80%;         left: 20%;         animation-delay: 4s;     }
    .sphere:nth-child(4) {         width: 100px;         height: 100px;         top: 30%;         right: 30%;         animation-delay: 1s;     }
    .sphere:nth-child(5) {         width: 90px;         height: 90px;         top: 10%;         left: 60%;         animation-delay: 3s;     }
    @keyframes float {         0%, 100% { transform: translateY(0px) rotate(0deg); }         50% { transform: translateY(-20px) rotate(180deg); }     }
    .container {         position: relative;         z-index: 1;         min-height: 100vh;         display: flex;         flex-direction: column;     }
    .login-section {         flex: 1;         display: flex;         flex-direction: column;         justify-content: center;         align-items: center;         padding: 2rem;         text-align: center;     }
    .dashboard-section {         display: none;         flex-direction: column;         flex: 1;         padding: 2rem;         max-width: 1200px;         margin: 0 auto;         width: 100%;     }
    .logo {         background: rgba(255,255,255,0.9);         padding: 2rem;         border-radius: 20px;         margin-bottom: 2rem;         box-shadow: 0 10px 30px rgba(0,0,0,0.2);         backdrop-filter: blur(10px);     }
    .logo h1 {         margin: 0;         color: #2c5530;         font-size: 2.5rem;         font-weight: bold;     }
    .logo p {         margin: 0.5rem 0 0 0;         color: #4682B4;         font-size: 1.2rem;     }
    .login-form {         background: rgba(255,255,255,0.9);         padding: 3rem;         border-radius: 20px;         box-shadow: 0 15px 40px rgba(0,0,0,0.2);         backdrop-filter: blur(10px);         max-width: 400px;         width: 100%;         margin-top: 2rem;     }
    .login-form h2 {         margin: 0 0 2rem 0;         color: #2c5530;         font-size: 1.8rem;     }
    .form-group {         margin-bottom: 1.5rem;         text-align: left;     }
    .form-group label {         display: block;         margin-bottom: 0.5rem;         color: #2c5530;         font-weight: bold;     }
    .form-group input, .form-group select, .form-group textarea {         width: 100%;         padding: 1rem;         border: 2px solid #e0e0e0;         border-radius: 10px;         font-size: 1rem;         transition: all 0.3s ease;         box-sizing: border-box;         font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;     }
    .form-group input:focus, .form-group select:focus, .form-group textarea:focus {         outline: none;         border-color: #4682B4;         box-shadow: 0 0 10px rgba(70, 130, 180, 0.3);     }
    .login-btn, .action-btn {         width: 100%;         background: linear-gradient(45deg, #87CEEB, #6B8E23);         color: white;         border: none;         padding: 1rem;         border-radius: 10px;         font-size: 1.1rem;         font-weight: bold;         cursor: pointer;         transition: all 0.3s ease;         margin-top: 1rem;     }
    .login-btn:hover, .action-btn:hover {         transform: translateY(-2px);         box-shadow: 0 10px 25px rgba(0,0,0,0.2);     }
    .action-btn {         width: auto;         padding: 0.8rem 1.5rem;         font-size: 1rem;         margin-top: 0; /* Ajuste para botones dentro de contenedores */     }
    .action-btn.secondary {         background: #f0f0f0;         color: #2c5530;         border: 1px solid #ddd;     }
    .action-btn.secondary:hover {         background: #e0e0e0;         transform: none;     }
    .demo-ids {         background: rgba(255,255,255,0.8);         padding: 1.5rem;         border-radius: 15px;         margin-top: 2rem;         max-width: 400px;         width: 100%;     }
    .demo-ids h3 {         margin: 0 0 1rem 0;         color: #2c5530;         font-size: 1.2rem;     }
    .demo-id {         display: flex;         justify-content: space-between;         align-items: center;         padding: 0.5rem 0;         border-bottom: 1px solid #eee;         font-size: 0.9rem;     }
    .demo-id:last-child {         border-bottom: none;     }
    .demo-id .id-code {         font-weight: bold;         color: #4682B4;         cursor: pointer;     }
    .demo-id .id-code:hover {         text-decoration: underline;     }
    .error-message {         background: rgba(255, 0, 0, 0.1);         color: #d32f2f;         padding: 1rem;         border-radius: 10px;         margin-top: 1rem;         border: 1px solid rgba(255, 0, 0, 0.3);         display: none;     }
    .dashboard-header {         background: rgba(255,255,255,0.9);         padding: 1.5rem;         border-radius: 15px;         margin-bottom: 2rem;         display: flex;         justify-content: space-between;         align-items: center;         backdrop-filter: blur(10px);         flex-wrap: wrap;     }
    .header-controls {         display: flex;         gap: 1rem;         align-items: center;     }
    .dashboard-header h2 {         margin: 0;         color: #2c5530;     }
    .back-btn {         background: linear-gradient(45deg, #87CEEB, #6B8E23);         color: white;         border: none;         padding: 0.8rem 1.5rem;         border-radius: 10px;         cursor: pointer;         font-weight: bold;         transition: all 0.3s ease;     }
    .back-btn:hover {         transform: scale(1.05);         box-shadow: 0 5px 15px rgba(0,0,0,0.2);     }
    .dashboard-grid {         display: grid;         grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));         gap: 2rem;     }
    .dashboard-card {         background: rgba(255,255,255,0.9);         padding: 2rem;         border-radius: 15px;         box-shadow: 0 5px 20px rgba(0,0,0,0.1);         backdrop-filter: blur(10px);         transition: all 0.3s ease;         display: flex;         flex-direction: column;     }
    .dashboard-card:hover {         transform: translateY(-3px);         box-shadow: 0 10px 30px rgba(0,0,0,0.15);         cursor: pointer;     }
    .dashboard-card.non-clickable:hover {         transform: none;         box-shadow: 0 5px 20px rgba(0,0,0,0.1);         cursor: default;     }
    .dashboard-card h3 {         margin: 0 0 1rem 0;         color: #2c5530;         display: flex;         align-items: center;         gap: 0.5rem;     }
    .card-content {         color: #666;         line-height: 1.6;         flex-grow: 1;     }
    .grade-item, .schedule-item-summary, .subject-item, .material-item, .assignment-item {         display: flex;         justify-content: space-between;         align-items: center;         padding: 0.75rem 0;         border-bottom: 1px solid #eee;     }     .grade-item:last-child, .schedule-item-summary:last-child, .subject-item:last-child, .material-item:last-child, .assignment-item:last-child {         border-bottom: none;     }
    .grade {         font-weight: bold;         color: #4682B4;     }
    .schedule-item {         background: linear-gradient(45deg, rgba(135,206,235,0.1), rgba(107,142,35,0.1));         padding: 1rem;         border-radius: 8px;         margin-bottom: 0.5rem;     }
    .calendar-item {         border-left: 4px solid #6B8E23;         padding-left: 1rem;         margin-bottom: 1rem;     }     .calendar-item.holiday { border-color: #d32f2f; }     .calendar-item.event { border-color: #4682B4; }     .calendar-item.exam { border-color: #FFA500; }      .calendar-item strong { color: #2c5530; }
    .schedule-time {         font-weight: bold;         color: #2c5530;     }
    .announcement {         background: rgba(135,206,235,0.1);         padding: 1rem;         border-radius: 8px;         margin-bottom: 1rem;         border-left: 4px solid #4682B4;     }
    .announcement:last-child {         margin-bottom: 0;     }
    .announcement-date {         font-size: 0.9rem;         color: #666;         margin-bottom: 0.5rem;     }
    table {         width: 100%;         border-collapse: collapse;         margin-top: 1rem;     }     th, td {         padding: 0.8rem;         text-align: left;         border-bottom: 1px solid #ddd;     }     th {         background-color: rgba(107,142,35,0.1);         color: #2c5530;     }
    tr.clickable-row:hover {         background-color: rgba(107,142,35,0.05);         cursor: pointer;     }
    .status-entregado { color: green; font-weight: bold; }     .status-pendiente { color: orange; font-weight: bold; }     .attendance-toggle { cursor: pointer; }     .attendance-Presente { color: green; }     .attendance-Ausente { color: red; }     .attendance-Pendiente { color: grey; }
    /* --- ESTILOS PARA CALENDARIO ESTILO GOOGLE --- */     .calendar-container {         background: #fff;         border-radius: 15px;         box-shadow: 0 10px 30px rgba(0,0,0,0.1);         padding: 2rem;         margin-bottom: 2rem;     }
    .calendar-header {         display: flex;         justify-content: space-between;         align-items: center;         margin-bottom: 1.5rem;         color: #2c5530;     }
    .calendar-header h3 {         font-size: 1.8rem;         margin: 0;         color: #2c5530;     }
    .calendar-nav button {         background: none;         border: 1px solid #ddd;         border-radius: 5px;         padding: 0.5rem 1rem;         cursor: pointer;         font-size: 1rem;         color: #2c5530;         transition: background 0.2s;     }
    .calendar-nav button:hover {         background: #f0f0f0;     }
    .calendar-grid {         display: grid;         grid-template-columns: repeat(7, 1fr);         border: 1px solid #e0e0e0;         border-radius: 8px;     }
    .calendar-day-name {         background-color: #f5f5f5;         color: #666;         padding: 0.75rem 0.5rem;         text-align: center;         font-weight: bold;         border-bottom: 1px solid #e0e0e0;     }
    .calendar-day {         min-height: 100px;         border-right: 1px solid #e0e0e0;         border-bottom: 1px solid #e0e0e0;         padding: 5px;         overflow: hidden;         position: relative;         background-color: #fff;     }     .calendar-grid > div:nth-child(7n) { border-right: none; }     .calendar-grid > div:nth-last-child(-n+7) { border-bottom: none; }
    .day-number {         font-weight: bold;         font-size: 1.2rem;         color: #4682B4;         display: block;         margin-bottom: 0.5rem;         text-align: right;         padding: 0 5px;     }
    .day-number.today {         color: white;         background: #d32f2f;         border-radius: 50%;         display: inline-block;         padding: 2px 6px;     }
    .calendar-day.out-month {         background-color: #fafafa;         color: #ccc;     }     .calendar-day.out-month .day-number {         color: #ccc;     }
    .calendar-event {         font-size: 0.8rem;         padding: 2px 4px;         margin-bottom: 2px;         border-radius: 4px;         white-space: nowrap;         overflow: hidden;         text-overflow: ellipsis;         cursor: help;     }     .calendar-event.event { background-color: rgba(70, 130, 180, 0.7); color: white; }     .calendar-event.holiday { background-color: rgba(211, 47, 47, 0.7); color: white; }     .calendar-event.exam { background-color: rgba(255, 165, 0, 0.7); color: white; }
    .add-event-form {         margin-top: 2rem;         background: rgba(255,255,255,0.8);         padding: 2rem;         border-radius: 10px;         border: 1px solid #ddd;     }     .add-event-form button { margin-right: 0.5rem; margin-top: 1rem; width: auto; }
    @media (max-width: 768px) {         .logo h1 { font-size: 2rem; }         .login-form { padding: 2rem; margin: 1rem; }         .dashboard-header { flex-direction: column; gap: 1rem; text-align: center; }         .dashboard-grid { grid-template-columns: 1fr; }         .calendar-day { min-height: 60px; }         .day-number { font-size: 1rem; }         .calendar-event { font-size: 0.7rem; }         .calendar-header { flex-direction: column; gap: 1rem;}         .header-controls { margin-top: 1rem;}     }
</style>
   
   
   
   
   
   
       
           
Fundación MOVAPE/UNICEP
           
Portal Universitario Digital
       
       
           
🎓 Acceso al Portal
                           
                    Tipo de Usuario:                                             Selecciona tu tipo                         Estudiante                         Docente                         Administrador                                    
                                
                    ID de Usuario:                                    
                                 Ingresar al Portal                                     
                ID o tipo de usuario no válido. Por favor verifica tu información.            
       
       
           
🔍 IDs de Demostración
           
                Admin de Sistema:                 ADM-2024-001            
           
                María González - Ing. Industrial:                 EST-2024-001            
           
                Carlos Ruiz - Administración:                 EST-2024-002            
           
                Ana Sofía - Psicología:                 EST-2024-003            
           
                Docente Dr. Ana Mendoza:                 PROF-2024-101            
       
   
   
       
           
Dashboard
            🚪 Cerrar Sesión        
       
       
   
   
       
           
Sección Detallada
           
           
            🔙 Volver al Dashboard        
       
       
                
       
   
<script>      // --- DATA ---      let users = {          'EST-2024-001': { type: 'student', name: 'María González', career: 'Ingeniería Industrial', semester: '3° Cuatrimestre', modality: 'Sabatina', grades: [{ subject: 'Matemáticas Aplicadas', grade: '8.5' }, { subject: 'Procesos Industriales', grade: '9.2' }, { subject: 'Física General', grade: '7.8' }], schedule: [{ time: '08:00 - 10:00', subject: 'Matemáticas Aplicadas', room: 'Aula 201', professor: 'Prof. Dr. Ana Mendoza', day: 'Sábado' }, { time: '10:30 - 12:30', subject: 'Procesos Industriales', room: 'Lab. Industrial', professor: 'Prof. Ing. Ana Rodríguez', day: 'Sábado' }, { time: '14:00 - 16:00', subject: 'Física General', room: 'Aula 105', professor: 'Prof. Ing. Roberto Silva', day: 'Sábado' }] },          'EST-2024-002': { type: 'student', name: 'Carlos Ruiz', career: 'Administración de Empresas', semester: '5° Cuatrimestre', modality: 'Dominical', grades: [{ subject: 'Marketing Digital', grade: '9.1' }, { subject: 'Contabilidad Avanzada', grade: '8.7' }], schedule: [{ time: '09:00 - 11:00', subject: 'Marketing Digital', room: 'Aula 301', professor: 'Prof. Lic. Patricia López', day: 'Domingo' }] },          'EST-2024-003': { type: 'student', name: 'Ana Sofía Herrera', career: 'Psicología', semester: '4° Cuatrimestre', modality: 'Sabatina', grades: [{ subject: 'Psicología Cognitiva', grade: '9.3' }, { subject: 'Neuropsicología', grade: '8.8' }], schedule: [{ time: '08:00 - 10:00', subject: 'Psicología Cognitiva', room: 'Aula 301', professor: 'Prof. Dra. Carmen Vásquez', day: 'Sábado' }] },          'PROF-2024-101': { type: 'professor', name: 'Dr. Ana Mendoza', department: 'Facultad de Ingeniería', subjects: ['Matemáticas Aplicadas', 'Cálculo Diferencial'], classes: [{ subject: 'Matemáticas Aplicadas', room: 'Aula 201', students: ['EST-2024-001', 'EST-2024-003'] }, { subject: 'Cálculo Diferencial', room: 'Aula 203', students: ['EST-2024-002', 'EST-2024-004'] }] },          'PROF-2024-102': { type: 'professor', name: 'Ing. Roberto Silva', department: 'Facultad de Ciencias', subjects: ['Física General', 'Física Aplicada'], classes: [{ subject: 'Física General', room: 'Aula 105', students: ['EST-2024-001', 'EST-2024-005'] }, { subject: 'Física Aplicada', room: 'Lab. Física', students: ['EST-2024-001'] }] },          'ADM-2024-001': { type: 'admin', name: 'Admin de Sistema', department: 'Administración Central', accessLevel: 'SuperUsuario' }      };           let assignments = {          'Matemáticas Aplicadas': [{ title: 'Tarea 1: Derivadas', dueDate: '2025-10-15', submissions: { 'EST-2024-001': {status: 'Entregado', grade: null, feedback: ''}, 'EST-2024-003': {status: 'Pendiente', grade: null, feedback: ''} } }],          'Física General': [{ title: 'Reporte de Práctica 1', dueDate: '2025-10-20', submissions: { 'EST-2024-001': {status: 'Entregado', grade: 9.5, feedback: 'Excelente reporte, muy bien detallado.'}, 'EST-2024-005': {status: 'Pendiente', grade: null, feedback: ''} } }]      };      // --- CALENDARIO MODIFICADO ---      let schoolCalendar = [          { date: '2025-09-01', description: 'Inicio de Cuatrimestre Sep-Dic 2025', type: 'event' },          { date: '2025-09-16', description: 'Día de la Independencia de México', type: 'holiday' },          { date: '2025-10-12', description: 'Día de la Raza - Suspensión de clases', type: 'holiday' },          { date: '2025-10-27', description: 'Inicio de Primer Parcial', type: 'exam' },          { date: '2025-10-31', description: 'Entrega de Proyectos Finales (Tentativa)', type: 'event' },          { date: '2025-11-02', description: 'Día de Muertos', type: 'holiday' },          { date: '2025-11-20', description: 'Aniversario de la Revolución', type: 'holiday' },          { date: '2025-12-08', description: 'Inicio de Segundo Parcial', type: 'exam' },          { date: '2025-12-19', description: 'Fin de Cuatrimestre Sep-Dic 2025', type: 'event' },      ];      // --- GLOBAL STATE ---      let currentUserId = null;      let currentCalendarDate = new Date(2025, 9, 1); // Empezamos en Octubre de 2025 para la demo     const TODAY_DATE = new Date(2025, 9, 27); // 27 de octubre de 2025 (Hardcoded para consistencia)     // --- DOM ELEMENTS ---      const loginSection = document.getElementById('loginSection');      const mainDashboard = document.getElementById('mainDashboard');      const detailedSection = document.getElementById('detailedSection');      const dashboardTitle = document.getElementById('dashboardTitle');      const dashboardContent = document.getElementById('dashboardContent');      const sectionTitle = document.getElementById('sectionTitle');      const sectionContent = document.getElementById('sectionContent');      const errorMessage = document.getElementById('errorMessage');      const loginForm = document.getElementById('loginForm');      const headerControls = document.querySelector('.header-controls');      const calendarEventFormContainer = document.getElementById('calendar-event-form-container');     // --- HELPER FUNCTIONS ---      function fillId(id) {          document.getElementById('userId').value = id;          if (id.startsWith('EST-')) document.getElementById('userType').value = 'student';          else if (id.startsWith('PROF-')) document.getElementById('userType').value = 'professor';          else if (id.startsWith('ADM-')) document.getElementById('userType').value = 'admin';      }      function formatDate(date) {          const d = new Date(date);          const year = d.getFullYear();          let month = '' + (d.getMonth() + 1);          let day = '' + d.getDate();          if (month.length < 2) month = '0' + month;          if (day.length < 2) day = '0' + day;          return [year, month, day].join('-');      }      // --- LOGIN & LOGOUT LOGIC ---      function handleLogin(event) {          event.preventDefault();          const userIdInput = document.getElementById('userId').value;          const userTypeInput = document.getElementById('userType').value;          const user = users[userIdInput];          if (user && user.type === userTypeInput) {              currentUserId = userIdInput;              loginSection.style.display = 'none';              mainDashboard.style.display = 'flex';              errorMessage.style.display = 'none';              if (user.type === 'student') populateStudentDashboard(user);              else if (user.type === 'professor') populateProfessorDashboard(user);              else if (user.type === 'admin') populateAdminDashboard(user);          } else {              errorMessage.style.display = 'block';          }      }      function logout() {          currentUserId = null;          loginSection.style.display = 'flex';          mainDashboard.style.display = 'none';          detailedSection.style.display = 'none';          loginForm.reset();          headerControls.innerHTML = '';      }      // --- NAVIGATION ---      function backToDashboard() {          detailedSection.style.display = 'none';          mainDashboard.style.display = 'flex';          headerControls.innerHTML = '';          calendarEventFormContainer.innerHTML = ''; // Limpiar el formulario de evento         const user = users[currentUserId];          if (user.type === 'student') populateStudentDashboard(user);          else if (user.type === 'professor') populateProfessorDashboard(user);          else if (user.type === 'admin') populateAdminDashboard(user);      }      // --- DASHBOARD POPULATION ---      function populateStudentDashboard(user) {          dashboardTitle.textContent = `Bienvenido, ${user.name}`;          dashboardContent.innerHTML = `            
               
🧑‍🎓 Info Estudiante
               
                   
Carrera: ${user.career}
                   
Cuatrimestre: ${user.semester}
                   
Modalidad: ${user.modality}
               
           
           
               
📊 Mis Calificaciones
               
                    ${user.grades.map(g => `
${g.subject}${g.grade}
`).join('')}                    
Ver todas...
               
           
           
               
🗓️ Mi Horario
               
                    ${user.schedule.slice(0, 2).map(s => `
${s.time}${s.subject}
`).join('')}                    
Ver completo...
               
           
           
               
📝 Tareas Pendientes
               
                   
Tienes **2 tareas pendientes** y **1 por calificar**.
                   
Ver todas...
               
           
           
               
📅 Calendario Escolar
               
                   
Consulta fechas importantes del ciclo académico.
                    ${schoolCalendar.filter(e => new Date(e.date) >= TODAY_DATE).slice(0, 3).map(e => `
${e.date.slice(5)}: ${e.description}
`).join('')}                
           
        `;     }      function populateProfessorDashboard(user) {          dashboardTitle.textContent = `Bienvenido, ${user.name}`;          dashboardContent.innerHTML = `            
               
🧑‍🏫 Info Docente
               
                   
Departamento: ${user.department}
                   
Clases Asignadas: ${user.subjects.length}
               
           
           
               
📚 Gestionar Clases
               
                    ${user.subjects.map(s => `
${s}Ir a Clase
`).join('')}                    
Seleccionar clase...
               
           
           
               
📖 Material Académico
               
                   
Comparte y gestiona material de estudio con tus alumnos.
                   
Subir Material
               
           
           
               
📅 Calendario Escolar
               
                   
Consulta fechas importantes del ciclo académico.
                    ${schoolCalendar.filter(e => new Date(e.date) >= TODAY_DATE).slice(0, 3).map(e => `
${e.date.slice(5)}: ${e.description}
`).join('')}                
           
        `;     }      function populateAdminDashboard(user) {          dashboardTitle.textContent = `Panel de Administración, ${user.name}`;          dashboardContent.innerHTML = `            
               
🛡️ Info Admin
               
                   
Nivel de Acceso: ${user.accessLevel}
                   
Departamento: ${user.department}
               
           
           
               
👥 Gestión de Usuarios
               
                   
Visualizar y modificar perfiles de estudiantes y docentes.
                   
Ir a Gestión
               
           
           
               
📅 Calendario Escolar (Gestión)
               
                   
Consulta y **edita** los eventos académicos principales.
                   
Abrir Calendario
               
           
           
               
💻 Logs del Sistema
               
                   
Monitoreo de actividad y estado del portal.
                   
Ver Registros
               
           
        `;     }      // --- DETAILED VIEW LOGIC ---      function showDetailedView(viewType, context) {          const user = users[currentUserId];          if (!user) return;          mainDashboard.style.display = 'none';          detailedSection.style.display = 'flex';          sectionContent.innerHTML = '';          headerControls.innerHTML = '';          calendarEventFormContainer.innerHTML = ''; // Limpiar formulario al cambiar de vista         switch (viewType) {              case 'schoolCalendar':                  sectionTitle.textContent = '📅 Calendario Académico';                  if (user.type === 'admin') {                      headerControls.innerHTML = `➕ Añadir Evento`;                  }                  currentCalendarDate = new Date(TODAY_DATE.getFullYear(), TODAY_DATE.getMonth(), 1); // Reset al mes actual de la demo                 renderCalendar();                  break;              case 'studentGrades':                  sectionTitle.textContent = '📊 Mis Calificaciones';                  sectionContent.innerHTML = '
Detalle de Calificaciones
Aquí se listarán todas tus calificaciones por materia.
';                  break;              case 'studentSchedule':                  sectionTitle.textContent = '🗓️ Mi Horario Completo';                  sectionContent.innerHTML = '
Horario Semanal
Aquí

