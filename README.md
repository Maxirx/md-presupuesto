# Documento funcional del MVP
## App de presupuestos para talleres de vehículos

### 1. Objetivo del producto
Desarrollar una app móvil orientada inicialmente a dueños o encargados de talleres de vehículos, que les permita crear presupuestos personalizados de forma rápida, profesional y reutilizable, incorporando:

- logo del taller
- firma
- leyenda o condiciones comerciales
- datos del cliente
- datos del vehículo
- productos y servicios cargados por el propio usuario
- generación de PDF
- envío por WhatsApp o medios similares
- historial de presupuestos

El enfoque inicial será **talleres mecánicos y de servicios para vehículos**, con posibilidad de expansión posterior a otros rubros.

---

### 2. Alcance del MVP
El MVP tendrá como finalidad validar si un taller puede resolver su proceso comercial básico de presupuestación desde el celular, sin depender de plantillas manuales, Word o diseños improvisados.

El MVP **sí incluye**:

- registro del usuario/taller
- configuración del perfil comercial
- alta y edición de clientes
- alta y edición de vehículos
- alta y edición de productos y servicios propios
- creación de presupuestos
- generación de PDF personalizado
- compartir presupuesto
- historial y consulta de presupuestos

El MVP **no incluye por ahora**:

- facturación electrónica
- stock real
- agenda de turnos
- múltiples usuarios por taller
- órdenes de trabajo completas
- seguimiento de pagos
- firma del cliente en pantalla
- integración con AFIP/ARCA
- reportes avanzados

---

### 3. Usuario objetivo
#### Usuario principal
Dueño, encargado o responsable comercial de un taller de vehículos.

#### Perfil del usuario
- trabaja desde el celular o desde contextos operativos
- necesita cotizar rápido
- suele repetir productos o servicios frecuentes
- necesita que el presupuesto tenga imagen profesional
- quiere enviar el presupuesto inmediatamente al cliente
- necesita conservar historial por cliente o por patente

---

### 4. Problema que resuelve
Hoy muchos talleres generan presupuestos de manera manual o semimanual:

- escribiéndolos por WhatsApp
- usando notas del celular
- usando Word o Excel sin formato estandarizado
- reutilizando archivos viejos
- sin base de clientes ni vehículos
- sin historial claro de presupuestos enviados

Esto genera:

- pérdida de tiempo
- errores de carga
- imagen poco profesional
- dificultad para reutilizar presupuestos
- poca trazabilidad comercial

La app busca resolver ese problema con un flujo simple, ordenado y móvil.

---

### 5. Propuesta de valor
La app permitirá que un taller:

- cree presupuestos profesionales en minutos
- reutilice productos y servicios ya cargados
- asocie cada presupuesto a un cliente y a un vehículo
- agregue logo, firma y leyendas propias
- genere un PDF prolijo
- lo comparta de inmediato
- conserve historial por cliente, vehículo y fecha

---

### 6. Módulos funcionales del MVP
## 6.1 Registro y perfil del taller
### Objetivo
Permitir que el vendedor/taller se dé de alta y configure los datos que se usarán en los presupuestos.

### Funcionalidades
- registro de usuario
- inicio de sesión
- edición del perfil comercial
- carga de logo
- carga de firma
- carga de leyenda o condiciones

### Datos del perfil
- nombre del taller o razón social
- nombre del responsable
- teléfono
- email
- dirección
- logo
- firma
- leyenda fija
- moneda por defecto
- validez sugerida del presupuesto
- observaciones comerciales opcionales

### Regla
Toda salida PDF debe tomar por defecto estos datos del perfil del taller.

---

## 6.2 Gestión de clientes
### Objetivo
Permitir registrar y reutilizar clientes en futuros presupuestos.

### Funcionalidades
- alta de cliente
- edición de cliente
- listado de clientes
- búsqueda por nombre, teléfono o documento

### Datos del cliente
- nombre y apellido o razón social
- DNI/CUIT opcional
- teléfono
- email
- dirección
- observaciones opcionales

### Reglas
- un cliente puede tener uno o más vehículos
- un cliente puede tener uno o más presupuestos

---

## 6.3 Gestión de vehículos
### Objetivo
Asociar cada presupuesto a un vehículo específico.

### Funcionalidades
- alta de vehículo
- edición de vehículo
- listado de vehículos por cliente
- búsqueda por patente

### Datos del vehículo
- cliente asociado
- patente
- marca
- modelo
- año opcional
- color opcional
- observaciones opcionales

### Reglas
- un vehículo pertenece a un cliente
- un vehículo puede tener múltiples presupuestos
- la patente debe ser un dato central de búsqueda

---

## 6.4 Gestión de productos y servicios
### Objetivo
Permitir que cada taller cargue sus propios ítems reutilizables, sin depender de un catálogo global.

### Funcionalidades
- alta de ítems
- edición de ítems
- activar/desactivar ítems
- listado de ítems
- filtro por tipo
- búsqueda por nombre

### Tipos de ítems
- producto
- servicio

### Datos del ítem
- nombre
- tipo
- descripción opcional
- precio unitario
- unidad opcional
- estado activo/inactivo

### Ejemplos
- Aceite 15W40
- Filtro de aceite
- Pastillas de freno
- Diagnóstico electrónico
- Mano de obra cambio de embrague
- Reparación tren delantero

### Reglas
- los ítems pertenecen al usuario/taller
- un ítem inactivo no debe aparecer por defecto al crear un nuevo presupuesto
- el precio puede editarse al momento de presupuestar

---

## 6.5 Creación de presupuesto
### Objetivo
Permitir crear un presupuesto personalizado y exportarlo.

### Flujo funcional
1. seleccionar cliente o crear uno nuevo
2. seleccionar vehículo o crear uno nuevo
3. agregar productos y servicios
4. editar cantidades y precios
5. agregar observaciones
6. aplicar condiciones y leyenda
7. previsualizar
8. generar PDF
9. compartir

### Datos del presupuesto
- número interno
- fecha
- cliente
- vehículo
- detalle de ítems
- subtotal
- descuento opcional
- total
- observaciones
- leyenda
- firma
- estado

### Estados mínimos
- borrador
- emitido
- enviado

### Reglas
- debe poder guardarse como borrador
- los precios de los ítems se pueden modificar dentro del presupuesto sin alterar necesariamente el precio base del ítem maestro
- el presupuesto debe mantener una copia del texto usado en cada línea, aun si luego el ítem original cambia

---

## 6.6 Generación de PDF
### Objetivo
Emitir un presupuesto con apariencia profesional y reutilizable.

### El PDF debe incluir
- logo del taller
- datos del taller
- datos del cliente
- datos del vehículo
- fecha
- número de presupuesto
- detalle de productos y servicios
- subtotal
- descuento si corresponde
- total
- observaciones
- leyenda o condiciones
- firma

### Contenidos recomendables para taller
- diagnóstico
- trabajo sugerido
- aclaración sobre repuestos incluidos o no incluidos
- validez del presupuesto

### Reglas
- el diseño debe ser limpio y legible
- el PDF debe poder verse bien en celular y compartirse fácilmente
- debe mantenerse una versión congelada del presupuesto emitido

---

## 6.7 Compartir presupuesto
### Objetivo
Permitir enviar rápidamente el presupuesto generado.

### Canales iniciales
- WhatsApp
- email
- descarga local
- impresión

### Regla
El flujo de compartir debe partir desde el PDF ya generado.

---

## 6.8 Historial de presupuestos
### Objetivo
Permitir consultar presupuestos anteriores.

### Funcionalidades
- listado cronológico
- búsqueda por cliente
- búsqueda por patente
- búsqueda por número de presupuesto
- filtro por estado

### Reglas
- el historial debe mostrar fecha, cliente, vehículo, total y estado
- se podrá abrir un presupuesto anterior para consulta
- en una etapa siguiente podrá duplicarse, pero no es indispensable en esta versión

---

### 7. Entidades del sistema
## 7.1 Usuario/Taller
Campos sugeridos:
- id
- nombre_taller
- responsable
- teléfono
- email
- dirección
- logo_url
- firma_url
- leyenda
- moneda
- validez_default
- created_at
- updated_at

## 7.2 Cliente
Campos sugeridos:
- id
- usuario_id
- nombre
- documento
- teléfono
- email
- dirección
- observaciones
- created_at
- updated_at

## 7.3 Vehículo
Campos sugeridos:
- id
- usuario_id
- cliente_id
- patente
- marca
- modelo
- año
- color
- observaciones
- created_at
- updated_at

## 7.4 Ítem
Campos sugeridos:
- id
- usuario_id
- tipo
- nombre
- descripción
- precio_unitario
- unidad
- activo
- created_at
- updated_at

## 7.5 Presupuesto
Campos sugeridos:
- id
- usuario_id
- cliente_id
- vehiculo_id
- numero
- fecha
- estado
- observaciones
- leyenda_aplicada
- subtotal
- descuento
- total
- pdf_url opcional
- created_at
- updated_at

## 7.6 Detalle de presupuesto
Campos sugeridos:
- id
- presupuesto_id
- item_id opcional
- tipo
- descripcion
- cantidad
- precio_unitario
- total_linea
- orden

---

### 8. Reglas de negocio iniciales
1. Cada usuario gestiona solo su propia información.
2. Cada cliente pertenece a un único usuario/taller.
3. Cada vehículo pertenece a un cliente y a un usuario.
4. Cada ítem pertenece al usuario que lo creó.
5. Un presupuesto debe quedar asociado a un cliente y a un vehículo.
6. El detalle del presupuesto debe persistir como snapshot, aunque luego cambien los ítems maestros.
7. La patente debe ser un criterio prioritario de búsqueda.
8. El perfil del taller define por defecto logo, firma y leyenda.
9. El presupuesto puede emitirse aun si el precio del ítem fue editado manualmente para ese caso puntual.
10. El historial debe conservar el presupuesto emitido sin depender de cambios posteriores del perfil.

---

### 9. Flujo principal del usuario
## Caso de uso principal
**Crear y enviar un presupuesto**

1. El usuario inicia sesión.
2. Selecciona “Nuevo presupuesto”.
3. Busca o crea un cliente.
4. Busca o crea un vehículo.
5. Agrega productos y servicios.
6. Ajusta cantidades, precios y observaciones.
7. Revisa subtotal y total.
8. Genera la vista previa.
9. Exporta el PDF.
10. Lo comparte por WhatsApp o email.
11. El presupuesto queda guardado en el historial.

---

### 10. Pantallas del MVP
## 10.1 Pantalla de acceso
- registro
- login
- recuperación básica de acceso

## 10.2 Pantalla de perfil del taller
- datos comerciales
- logo
- firma
- leyenda
- configuración general

## 10.3 Pantalla de clientes
- listado
- búsqueda
- alta
- edición

## 10.4 Pantalla de vehículos
- listado por cliente
- alta
- edición
- búsqueda por patente

## 10.5 Pantalla de productos y servicios
- listado
- filtros
- alta
- edición
- activación/inactivación

## 10.6 Pantalla de nuevo presupuesto
- selección de cliente
- selección de vehículo
- carga de ítems
- edición de cantidades y precios
- observaciones
- totalización

## 10.7 Pantalla de vista previa
- visualización del documento
- confirmación final
- generar PDF

## 10.8 Pantalla de historial
- listado de presupuestos
- filtros
- búsqueda
- apertura de detalle

---

### 11. Criterios de éxito del MVP
El MVP será exitoso si un taller puede:

- registrarse sin fricción
- cargar sus datos comerciales
- cargar clientes y vehículos
- cargar sus propios servicios y productos
- generar un presupuesto profesional en pocos minutos
- enviarlo inmediatamente
- recuperarlo luego desde el historial

Indicadores posibles:
- tiempo medio para crear primer presupuesto
- cantidad de presupuestos generados por usuario
- porcentaje de usuarios que cargan logo/firma
- frecuencia de reutilización de ítems
- consultas al historial por patente o cliente

---

### 12. Riesgos y decisiones de diseño
## Riesgos
- sobrecargar el MVP con funciones contables o administrativas
- diseñarlo demasiado genérico y perder foco en talleres
- no modelar bien vehículo/cliente desde el inicio
- generar PDF poco claro o poco práctico en celular

## Decisiones recomendadas
- mantener foco inicial en talleres
- separar cliente y vehículo desde el comienzo
- tratar productos y servicios como ítems del usuario
- guardar snapshot del presupuesto emitido
- priorizar velocidad de uso antes que complejidad

---

### 13. Evolución futura posible
Una vez validado el MVP, se podrá extender a:

- orden de trabajo
- autorización del cliente
- firma en pantalla
- adjuntar fotos del vehículo
- historial mecánico por vehículo
- facturación
- control de pagos
- varios usuarios por taller
- estadísticas comerciales
- plantillas por rubro
- expansión a otros oficios técnicos

---

### 14. Recomendación tecnológica inicial
Para esta versión del producto, una arquitectura razonable sería:

- **Frontend móvil:** React Native con Expo
- **Backend / base de datos:** Supabase o Firebase
- **Storage:** para logo, firma y PDFs
- **Generación de PDF:** plantilla HTML renderizada a PDF

Esto permitiría:
- salir rápido a producción
- mantener una sola base móvil
- escalar luego a más rubros
- agregar autenticación y almacenamiento sin complejidad excesiva

---

### 15. Definición resumida del MVP
**MVP 1: App de presupuestos para talleres de vehículos**

Permite que un taller:
- se registre
- configure su identidad comercial
- cargue clientes
- cargue vehículos
- cargue sus propios productos y servicios
- genere presupuestos en PDF
- los comparta
- mantenga historial

El foco principal del MVP no será la administración total del taller, sino la **presupuestación rápida, profesional y reutilizable desde el celular**.


---

# 16. Backlog inicial del producto (MVP)
El backlog se organiza por **épicas → funcionalidades → tareas técnicas**.

Las estimaciones de costo se presentan en tres escenarios:
- desarrollo propio
- desarrollador freelance
- pequeño equipo

Los costos están expresados de forma orientativa en **USD** para facilitar comparación.

---

# 16.1 Épica 1 — Autenticación y registro de usuario
Objetivo: permitir que un taller cree su cuenta y acceda a la aplicación.

## Funcionalidades
- registro de usuario
- login
- recuperación de contraseña
- sesión persistente

## Tareas técnicas
- pantalla de registro
- validación de email
- autenticación con backend
- manejo de sesión
- cierre de sesión

## Estimación técnica
Complejidad: baja
Tiempo estimado: 2 a 4 días

## Costos posibles
Desarrollo propio: 0 USD
Freelance: 200 – 600 USD
Equipo pequeño: 800 – 1500 USD

Infraestructura posible:
- Supabase Auth: gratis hasta cierto uso
- Firebase Auth: gratis en plan inicial

Costo mensual estimado inicial: 0 USD

---

# 16.2 Épica 2 — Perfil del taller
Objetivo: configurar la identidad comercial que aparecerá en los presupuestos.

## Funcionalidades
- edición de datos del taller
- carga de logo
- carga de firma
- leyenda comercial
- moneda

## Tareas técnicas
- pantalla de perfil
- subida de imágenes
- almacenamiento en storage
- guardado en base de datos

## Estimación técnica
Complejidad: baja
Tiempo estimado: 3 a 5 días

## Costos posibles
Freelance: 300 – 800 USD
Equipo pequeño: 1000 – 2000 USD

Infraestructura:
Storage para imágenes

Costo mensual estimado:
Supabase storage o Firebase storage
0 – 5 USD

---

# 16.3 Épica 3 — Gestión de clientes
Objetivo: registrar y reutilizar clientes.

## Funcionalidades
- alta de cliente
- edición de cliente
- listado
- búsqueda

## Tareas técnicas
- pantalla lista clientes
- pantalla alta cliente
- base de datos clientes
- búsqueda local

## Estimación técnica
Complejidad: baja
Tiempo estimado: 3 a 5 días

## Costos posibles
Freelance: 300 – 700 USD
Equipo pequeño: 1000 – 2000 USD

Costo infraestructura: incluido en base de datos

---

# 16.4 Épica 4 — Gestión de vehículos
Objetivo: asociar vehículos a clientes.

## Funcionalidades
- alta vehículo
- edición vehículo
- listado por cliente
- búsqueda por patente

## Tareas técnicas
- pantalla alta vehículo
- pantalla listado
- modelo base de datos

## Estimación técnica
Complejidad: baja
Tiempo estimado: 3 a 5 días

## Costos posibles
Freelance: 300 – 700 USD
Equipo pequeño: 1000 – 2000 USD

---

# 16.5 Épica 5 — Productos y servicios
Objetivo: permitir crear ítems reutilizables.

## Funcionalidades
- alta de ítems
- edición
- activación/inactivación
- listado

## Tareas técnicas
- base de datos items
- pantalla listado
- pantalla alta item

## Estimación técnica
Complejidad: baja
Tiempo estimado: 4 a 6 días

## Costos posibles
Freelance: 400 – 900 USD
Equipo pequeño: 1200 – 2500 USD

---

# 16.6 Épica 6 — Creación de presupuesto
Esta es la funcionalidad central del sistema.

## Funcionalidades
- crear presupuesto
- agregar ítems
- modificar cantidades
- subtotal
- total
- observaciones

## Tareas técnicas
- pantalla creación presupuesto
- selección cliente
- selección vehículo
- agregar líneas de detalle
- cálculo automático

## Estimación técnica
Complejidad: media
Tiempo estimado: 7 a 12 días

## Costos posibles
Freelance: 900 – 2000 USD
Equipo pequeño: 2500 – 4500 USD

---

# 16.7 Épica 7 — Generación de PDF
Objetivo: generar el presupuesto final.

## Funcionalidades
- vista previa
- generar PDF
- incluir logo y firma

## Tareas técnicas
- plantilla HTML
- render PDF
- guardar archivo

## Estimación técnica
Complejidad: media
Tiempo estimado: 5 a 8 días

## Costos posibles
Freelance: 600 – 1500 USD
Equipo pequeño: 2000 – 3500 USD

---

# 16.8 Épica 8 — Compartir presupuesto
Objetivo: enviar el presupuesto al cliente.

## Funcionalidades
- compartir PDF
- enviar por WhatsApp
- enviar por email

## Tareas técnicas
- integración share mobile
- manejo archivos

## Estimación técnica
Complejidad: baja
Tiempo estimado: 2 a 4 días

## Costos posibles
Freelance: 200 – 600 USD
Equipo pequeño: 800 – 1500 USD

---

# 16.9 Épica 9 — Historial de presupuestos
Objetivo: consultar presupuestos emitidos.

## Funcionalidades
- listado
- filtros
- búsqueda por cliente
- búsqueda por patente

## Tareas técnicas
- pantalla historial
- consultas base de datos

## Estimación técnica
Complejidad: media
Tiempo estimado: 4 a 7 días

## Costos posibles
Freelance: 500 – 1200 USD
Equipo pequeño: 1500 – 3000 USD

---

# 17. Estimación global del MVP

## Tiempo total estimado
Entre 5 y 9 semanas de desarrollo.

## Costos aproximados

Desarrollo propio:
0 USD (solo tiempo)

Freelance:
3500 – 8000 USD

Equipo pequeño:
9000 – 20000 USD

---

# 18. Costos de infraestructura mensuales estimados

## Base de datos y backend
Supabase o Firebase

Costo inicial: gratis

Escala pequeña:
0 – 25 USD/mes

---

## Storage
Para logos, firmas y PDFs

0 – 10 USD/mes

---

## Dominio web (si hay landing)

10 – 15 USD/año

---

## Publicación app stores

Google Play
25 USD pago único

Apple App Store
99 USD/año

---

# 19. Costos totales operativos estimados

Primer año aproximado:

Infraestructura:
0 – 300 USD

Publicación stores:
124 USD

Total anual inicial:
124 – 424 USD

---

# 20. Conclusión económica

Este tipo de app tiene **costos de infraestructura extremadamente bajos** en relación a otros productos SaaS.

El costo principal es el **desarrollo inicial del MVP**.

Una vez lanzada, la app puede operar con pocos usuarios prácticamente sin costo y escalar progresivamente.


---

# 21. Modelo de base de datos / entidades
El objetivo de este modelo es cubrir correctamente el MVP para talleres, evitando dos errores comunes:

1. modelar el sistema como si solo existieran clientes y presupuestos
2. acoplar demasiado el presupuesto a los ítems vivos, perdiendo trazabilidad histórica

La propuesta separa claramente:
- usuario/taller
- cliente
- vehículo
- ítems reutilizables
- presupuesto
- detalle congelado del presupuesto

---

## 21.1 Criterios de modelado
### Principios
- cada taller ve solo sus propios datos
- un cliente puede tener varios vehículos
- un vehículo puede tener varios presupuestos
- un presupuesto debe conservar snapshot histórico
- productos y servicios comparten una misma entidad base de ítem
- el PDF emitido puede guardarse como archivo asociado al presupuesto

### Alcance del modelo
Este modelo está pensado para el MVP, pero deja preparada la evolución futura hacia:
- órdenes de trabajo
- pagos
- facturación
- múltiples usuarios por taller
- historial técnico del vehículo

---

## 21.2 Entidad: users
Representa la cuenta autenticada.

### Campos sugeridos
- id (uuid, pk)
- email
- password_hash o auth_provider_id
- created_at
- updated_at
- is_active

### Observaciones
- si se usa Supabase Auth o Firebase Auth, parte de esta entidad puede delegarse al sistema de autenticación
- para el MVP, puede bastar con enlazar el usuario autenticado al perfil del taller

---

## 21.3 Entidad: workshops
Representa el perfil comercial del taller o negocio.

### Campos sugeridos
- id (uuid, pk)
- user_id (fk → users.id)
- business_name
- owner_name
- phone
- email
- address
- tax_id opcional
- logo_url
- signature_url
- default_legend
- default_currency
- default_validity_days opcional
- created_at
- updated_at

### Regla clave
Un usuario del MVP tendrá un único taller asociado.

### Relación
- 1 user → 1 workshop

---

## 21.4 Entidad: clients
Representa al cliente del taller.

### Campos sugeridos
- id (uuid, pk)
- workshop_id (fk → workshops.id)
- client_type (person / company)
- full_name_or_business_name
- document_number opcional
- tax_id opcional
- phone
- email
- address
- notes
- created_at
- updated_at
- deleted_at opcional

### Reglas
- cada cliente pertenece a un taller
- el borrado conviene que sea lógico, no físico

### Relación
- 1 workshop → N clients

---

## 21.5 Entidad: vehicles
Representa el vehículo sobre el cual se presupuestan trabajos.

### Campos sugeridos
- id (uuid, pk)
- workshop_id (fk → workshops.id)
- client_id (fk → clients.id)
- plate_number
- brand
- model
- year opcional
- color opcional
- vin opcional
- engine_number opcional
- notes
- created_at
- updated_at
- deleted_at opcional

### Reglas
- cada vehículo pertenece a un cliente
- cada vehículo también queda dentro del alcance del taller
- la patente debe indexarse

### Relación
- 1 client → N vehicles
- 1 workshop → N vehicles

### Nota de diseño
Aunque vehicle depende de client, se recomienda conservar también workshop_id para simplificar filtros, seguridad y consultas.

---

## 21.6 Entidad: items
Representa los productos y servicios reutilizables del taller.

### Campos sugeridos
- id (uuid, pk)
- workshop_id (fk → workshops.id)
- item_type (product / service)
- name
- description
- unit_label opcional
- default_unit_price
- is_active
- created_at
- updated_at
- deleted_at opcional

### Reglas
- los ítems pertenecen al taller
- el precio base es editable al presupuestar
- no deben eliminarse físicamente si ya fueron usados en presupuestos

### Relación
- 1 workshop → N items

---

## 21.7 Entidad: quotes
Representa la cabecera del presupuesto.

### Campos sugeridos
- id (uuid, pk)
- workshop_id (fk → workshops.id)
- client_id (fk → clients.id)
- vehicle_id (fk → vehicles.id)
- quote_number
- status (draft / issued / sent / accepted / rejected opcional)
- issue_date
- validity_date opcional
- currency
- subtotal_amount
- discount_amount
- tax_amount opcional
- total_amount
- notes
- diagnostic_text opcional
- recommended_work_text opcional
- included_disclaimer opcional
- legend_snapshot
- workshop_name_snapshot
- workshop_phone_snapshot opcional
- workshop_email_snapshot opcional
- workshop_address_snapshot opcional
- logo_url_snapshot opcional
- signature_url_snapshot opcional
- pdf_url opcional
- sent_at opcional
- created_at
- updated_at
- deleted_at opcional

### Reglas
- quote_number debe ser único por taller
- la tabla debe conservar snapshots de los datos visibles del taller y la leyenda
- el presupuesto no debe depender exclusivamente del perfil vivo del taller

### Relación
- 1 workshop → N quotes
- 1 client → N quotes
- 1 vehicle → N quotes

### Nota clave
Los snapshots son importantes. Si el taller cambia logo, teléfono o leyenda, los presupuestos viejos no deben alterarse.

---

## 21.8 Entidad: quote_lines
Representa cada línea del presupuesto.

### Campos sugeridos
- id (uuid, pk)
- quote_id (fk → quotes.id)
- item_id opcional (fk → items.id)
- line_order
- item_type_snapshot
- description_snapshot
- unit_label_snapshot opcional
- quantity
- unit_price
- line_total
- notes opcional
- created_at
- updated_at

### Reglas
- item_id puede ser nulo para permitir líneas manuales
- description_snapshot debe guardarse siempre
- el detalle debe sobrevivir aunque el ítem original cambie o se desactive

### Relación
- 1 quote → N quote_lines
- 0..1 item → N quote_lines

### Ejemplo
Un presupuesto podría tener:
- Mano de obra cambio de embrague
- Kit de embrague
- Rectificación volante
- Observación manual no vinculada a ningún ítem guardado

---

## 21.9 Entidad opcional: quote_files
Sirve si querés desacoplar archivos del presupuesto.

### Campos sugeridos
- id (uuid, pk)
- quote_id (fk → quotes.id)
- file_type (pdf / image / other)
- file_url
- file_name
- created_at

### Cuándo conviene
- si querés permitir más adelante varias versiones PDF
- si querés adjuntar fotos del vehículo o documentos

### Para MVP
Puede omitirse y usar solo pdf_url dentro de quotes.

---

## 21.10 Entidades futuras recomendadas
No forman parte del MVP, pero el modelo actual debería permitir agregarlas sin rehacer todo.

### work_orders
Para convertir presupuesto aprobado en orden de trabajo.

### payments
Para registrar cobros parciales o totales.

### invoices
Para asociar facturación.

### workshop_users
Para soportar varios usuarios por taller.

### vehicle_service_history
Para historial mecánico del vehículo.

---

# 22. Relaciones principales
## Relaciones 1 a N
- workshop → clients
- workshop → vehicles
- workshop → items
- workshop → quotes
- client → vehicles
- client → quotes
- vehicle → quotes
- quote → quote_lines

## Relaciones opcionales
- item → quote_lines
- quote → quote_files

---

# 23. Diagrama relacional textual
```text
users
  └── workshops
        ├── clients
        │     └── vehicles
        ├── items
        └── quotes
              └── quote_lines
```

Versión más detallada:

```text
users (1) ───── (1) workshops
workshops (1) ── (N) clients
workshops (1) ── (N) vehicles
workshops (1) ── (N) items
workshops (1) ── (N) quotes
clients (1) ───── (N) vehicles
clients (1) ───── (N) quotes
vehicles (1) ──── (N) quotes
quotes (1) ────── (N) quote_lines
items (1) ─────── (N) quote_lines [opcional]
```

---

# 24. Reglas de integridad recomendadas
## Integridad lógica
- no permitir quote sin client_id
- no permitir quote sin vehicle_id
- no permitir quote sin al menos una línea
- no permitir line_total negativo
- no permitir quantity menor o igual a cero
- no permitir unit_price negativo

## Integridad de pertenencia
- vehicle.workshop_id debe coincidir con client.workshop_id
- quote.workshop_id debe coincidir con client.workshop_id y vehicle.workshop_id
- item.workshop_id debe coincidir con quote.workshop_id cuando se use item_id

## Integridad histórica
- quote debe guardar snapshots visibles
- quote_lines debe guardar descripción y precio usados al momento de emitir

---

# 25. Índices recomendados
Para que el MVP responda bien en búsquedas, conviene indexar:

## clients
- workshop_id
- full_name_or_business_name
- phone
- document_number

## vehicles
- workshop_id
- client_id
- plate_number

## items
- workshop_id
- item_type
- name
- is_active

## quotes
- workshop_id
- quote_number
- client_id
- vehicle_id
- status
- issue_date

## quote_lines
- quote_id
- item_id

### Nota importante
En vehicles.plate_number conviene usar una versión normalizada para búsqueda:
- sin espacios
- sin guiones
- en mayúsculas

---

# 26. Decisiones de modelado importantes
## 26.1 Por qué separar cliente y vehículo
Porque en un taller el trabajo real se hace sobre un vehículo, no solo sobre una persona. Además:
- un mismo cliente puede tener varios vehículos
- la búsqueda por patente es crítica
- el historial futuro debe construirse por vehículo

## 26.2 Por qué unificar productos y servicios en items
Porque para presupuestar ambos se comportan parecido:
- tienen nombre
- descripción
- precio
- pueden agregarse como línea

Se distinguen con item_type.

## 26.3 Por qué guardar snapshots
Porque el presupuesto es un documento histórico. Si mañana cambia el precio del ítem, el teléfono del taller o la leyenda legal, el presupuesto emitido debe seguir igual.

## 26.4 Por qué permitir item_id nulo en quote_lines
Porque en la práctica el taller a veces necesita cargar una línea única o excepcional sin crearla como ítem reusable.

---

# 27. Campos mínimos obligatorios por entidad
## workshops
- user_id
- business_name

## clients
- workshop_id
- full_name_or_business_name

## vehicles
- workshop_id
- client_id
- plate_number
- brand
- model

## items
- workshop_id
- item_type
- name
- default_unit_price

## quotes
- workshop_id
- client_id
- vehicle_id
- quote_number
- status
- issue_date
- currency
- subtotal_amount
- total_amount
- legend_snapshot
- workshop_name_snapshot

## quote_lines
- quote_id
- line_order
- description_snapshot
- quantity
- unit_price
- line_total

---

# 28. Ejemplo de registro real
## Cliente
- full_name_or_business_name: Juan Pérez
- phone: 387xxxxxxx

## Vehículo
- plate_number: AB123CD
- brand: Toyota
- model: Hilux

## Ítems
1. service — Mano de obra cambio de pastillas — 45000
2. product — Pastillas de freno delanteras — 85000

## Presupuesto
- quote_number: P-000012
- subtotal_amount: 130000
- discount_amount: 0
- total_amount: 130000

## Líneas
1. Mano de obra cambio de pastillas — 1 × 45000
2. Pastillas de freno delanteras — 1 × 85000

---

# 29. Recomendación práctica para implementación
Si se implementa con Postgres o Supabase, la base puede arrancar con estas tablas:

- users o auth.users enlazado
- workshops
- clients
- vehicles
- items
- quotes
- quote_lines

Con eso ya se cubre correctamente el MVP.

No conviene empezar con más tablas si todavía no entran:
- pagos
- facturas
- stock
- sucursales
- múltiples usuarios

Porque agregar complejidad prematura va a enlentecer el desarrollo.

---

# 30. Conclusión del modelo
El núcleo correcto para este MVP es:

- **taller**
- **cliente**
- **vehículo**
- **ítem**
- **presupuesto**
- **detalle del presupuesto**

Ese modelo es suficientemente simple para construir rápido, pero suficientemente sólido para crecer luego hacia una solución más completa para talleres.
