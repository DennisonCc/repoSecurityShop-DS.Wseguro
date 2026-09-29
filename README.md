SecureShop
actividad 1
# SecureShop - Arquitectura de Microservicios

SecureShop es una plataforma de comercio electrónico orientada a la comercialización de productos tecnológicos a través de Internet. Para garantizar la escalabilidad, la evolución independiente de los componentes y la agilidad en los despliegues, la plataforma está diseñada mediante una arquitectura orientada a microservicios.

---

## 🏗️ Arquitectura del Sistema

El sistema consta de los siguientes componentes principales:

* **Cliente / Usuario:** Dispositivos o aplicaciones cliente que consumen los servicios del sistema mediante solicitudes HTTP (API REST).
* **API Gateway:** Punto único de entrada encargado de autenticar, enrutar y gestionar los requerimientos dirigidos a los microservicios del sistema.
* **User Service:** Microservicio dedicado a la gestión del ciclo de vida de los usuarios (registro, consulta y listado).
* **Product Service:** Microservicio responsable de la administración del catálogo de productos (registro, consulta, listado y actualización).
* **Order Service:** Microservicio encargado del procesamiento y seguimiento de los pedidos de compra (creación, consulta y listado).
* **Bases de Datos:** Persistencia desacoplada con una base de datos independiente para cada dominio/microservicio.

---

## 🔒 Actividad 1: Identificación y Clasificación de Activos

Como parte del análisis de seguridad del ciclo de vida del software, se han identificado, clasificado y evaluado los riesgos asociados a los principales activos del sistema SecureShop:

| Activo | Clasificación | Consecuencias de acceso no autorizado, modificación o indisponibilidad |
| :--- | :--- | :--- |
| **Datos personales de usuarios** | Datos / Información | **Acceso:** Violación de la privacidad de los clientes y posibles sanciones legales.<br>**Modificación:** Corrupción o alteración no autorizada de perfiles.<br>**Indisponibilidad:** Imposibilidad de inicio de sesión y de completar procesos de compra. |
| **Credenciales y Tokens de Autenticación** | Información sensible | **Acceso:** Suplantación de identidad de usuarios y administradores.<br>**Modificación:** Bloqueo masivo de cuentas y pérdida de acceso.<br>**Indisponibilidad:** Interrupción total del sistema de autenticación de la plataforma. |
| **Catálogo e Inventario de Productos** | Datos / Información | **Acceso:** Exposición de estrategias comerciales a competidores.<br>**Modificación:** Manipulación maliciosa de precios o stock, generando pérdidas financieras.<br>**Indisponibilidad:** Los clientes no pueden explorar ni seleccionar productos. |
| **Historial de Pedidos y Transacciones** | Datos / Información | **Acceso:** Revelación de información sensible de compra e historial comercial.<br>**Modificación:** Alteración de estados de envío o creación de órdenes fraudulentas.<br>**Indisponibilidad:** Freno en el procesamiento de despachos, facturación y soporte. |
| **Código Fuente de los Microservicios** | Software | **Acceso:** Exposición de la lógica de negocio e identificación de vulnerabilidades por atacantes.<br>**Modificación:** Inyección de código malicioso o puertas traseras (backdoors).<br>**Indisponibilidad:** Paralización del pipeline de integración y despliegue continuo (CI/CD). |
| **API Gateway** | Software / Servicio | **Acceso:** Mapeo no autorizado de las rutas y servicios internos.<br>**Modificación:** Redirección de tráfico hacia servicios maliciosos o deshabilitación de reglas de seguridad.<br>**Indisponibilidad:** Caída total del punto de entrada (Punto único de falla) dejando inalcanzable el sistema. |
| **Microservicio User Service** | Servicio / Software | **Acceso:** Acceso no autorizado a funciones de administración de usuarios.<br>**Modificación:** Comportamiento erróneo o evasión de validaciones de usuario.<br>**Indisponibilidad:** Imposibilidad de registrar o consultar cuentas de usuario. |
| **Microservicio Product Service** | Servicio / Software | **Acceso:** Interceptación o uso no autorizado del servicio de inventario.<br>**Modificación:** Alteración no autorizada en el flujo de actualización de productos.<br>**Indisponibilidad:** Falla generalizada al intentar buscar o agregar artículos al carrito. |
| **Microservicio Order Service** | Servicio / Software | **Acceso:** Manipulación no autorizada del flujo de pedidos.<br>**Modificación:** Alteración de importes, cantidades o estados de pedidos.<br>**Indisponibilidad:** Imposibilidad de procesar nuevas compras o consultar órdenes existentes. |
| **Bases de Datos por Dominio** | Infraestructura / Datos | **Acceso:** Exfiltración masiva de bases de datos críticas de la empresa.<br>**Modificación:** Pérdida, encriptación (Ransomware) o manipulación irrecuperable de información.<br>**Indisponibilidad:** Inoperatividad total de los microservicios por falta de capa de datos. |
