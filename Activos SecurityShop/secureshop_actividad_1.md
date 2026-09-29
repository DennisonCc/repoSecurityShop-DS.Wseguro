#  SecureShop - Actividad 1

### nombres:<br> 
Chalacan Dennison<br> 
Llumiquinga Jerson<br>
Sandoval Fernando<br>


## 1. Identificación y Clasificación de Activos


| Activo | Tipo | Consecuencia si es accedido, modificado o queda indisponible |
| :--- | :--- | :--- |
| **1. Datos personales de usuarios** | Información de usuarios / Datos | **Acceso no autorizado:** Violación de la privacidad del cliente y pérdida de reputación.<br>**Modificación:** Datos de envío o contacto erróneos, entregas fallidas o suplantación de identidad.<br>**Indisponibilidad:** Imposibilidad de validar la información de los clientes para procesar pedidos. |
| **2. Credenciales y tokens de autenticación** | Información de usuarios / Datos | **Acceso no autorizado:** amenaza masivo de cuentas de usuario y administración.<br>**Modificación:** Modificación no autorizada de contraseñas, provocando bloqueo masivo de usuarios.<br>**Indisponibilidad:** Imposibilidad de que los clientes o administradores inicien sesión en el sistema. |
| **3. Catálogo e inventario de productos** | Información de usuarios / Datos | **Acceso no autorizado:** Exposición de precios a competidores.<br>**Modificación:** Modificación  de precios  generando pérdidas.<br>**Indisponibilidad:** Los clientes no pueden ver ni buscar productos, deteniendo las ventas. |
| **4. Historial de pedidos y transacciones** | Información de usuario / Datos | **Acceso no autorizado:** Filtración del comportamiento de compra y hábitos del cliente.<br>**Modificación:** Alteración de estados de pedidos ,causa inventario incoherente.<br>**Indisponibilidad:** Imposibilidad de dar seguimiento a compras realizadas o generar reportes financieros. |
| **5. Código fuente de la aplicación** | Software | **Acceso no autorizado:** Exposición de vulnerabilidades del código, lógica de negocio o claves secretas .<br>**Modificación:** Inyección de código malicioso.<br>**Indisponibilidad:** Retraso total en el desarrollo, despliegue de correcciones y nuevas funcionalidades. |
| **6. API Gateway** | Servicio / Software | **Acceso no autorizado:**enrutamiento no autorizado a microservicios internos.<br>**Modificación:** Alteración de reglas de enrutamiento, derivando el tráfico a servidores ajenos.<br>**Indisponibilidad:** Caída total de la plataforma. |
| **7. User Service** | Servicio | **Acceso no autorizado:** Exposición directa de las interfaces de administración de usuarios.<br>**Modificación:** Modificación directa en la lógica de registro o consulta de usuarios.<br>**Indisponibilidad:** Imposibilidad de registrar nuevos clientes o autenticar a los existentes. |
| **8. Product Service** | Servicio | **Acceso no autorizado:** Extracción no autorizada de la base de productos mediante consultas no autenticadas.<br>**Modificación:** Alteración de la lógica de negocio para actualización o registro de productos.<br>**Indisponibilidad:** Los clientes no pueden navegar por el catálogo ni agregar productos al carrito. |
| **9. Order Service** | Servicio | **Acceso no autorizado:** problemas generados por la integración de pasarelas de pago.<br>**Modificación:** Creación no autorizada o alteración del flujo de pedidos.<br>**Indisponibilidad:** no se puede comprar adecuadamente . |
| **10. Bases de Datos de los Microservicios** | Infraestructura / Datos | **Acceso no autorizado:** Robos masivos de bases de datos (data breaches).<br>**Modificación:** Corrupción o eliminación de tablas de usuarios, productos o pedidos.<br>**Indisponibilidad:** Interrupción total de la persitencia del sistema, afectando la disponibilidad de todos los microservicios. |
