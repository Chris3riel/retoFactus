# Sistema de Facturación - Halltec

Este sistema de facturación es una aplicación web que permite crear y validar facturas electrónicas consumiendo la API de Factus. Está diseñado para facilitar la generación de facturas con información detallada del cliente, productos o servicios, y retenciones, integrándose con la plataforma de Factus para la validación y emisión de documentos fiscales.

## Características

- Formulario completo para ingresar datos generales de la factura.
- Definición del período de facturación con fechas y horas de inicio y fin.
- Registro detallado de datos del cliente, incluyendo identificación, dirección, y contacto.
- Gestión dinámica de productos o servicios con sus respectivos códigos, cantidades, precios, descuentos, impuestos y retenciones.
- Validación de la factura mediante la API de Factus, mostrando una respuesta estructurada con el estado, mensaje, información de la empresa, cliente, factura, productos y retenciones.
- Visualización de códigos QR y enlaces para consultar la factura en línea.

## Uso

1. Abrir el archivo `facturacion.html` en un navegador web.
2. Ingresar los datos requeridos en cada sección del formulario:
   - Información General: rango de numeración, código de referencia, observaciones, forma y método de pago, fecha de vencimiento.
   - Período de Facturación: fechas y horas de inicio y fin.
   - Datos del Cliente: identificación, DV, empresa, nombre comercial, nombres, dirección, email, teléfono, IDs legales y tributarios.
   - Productos/Servicios: agregar uno o más productos o servicios con sus detalles y retenciones.
3. Hacer clic en el botón **Validar Factura** para enviar los datos a la API de Factus.
4. Revisar la respuesta mostrada en pantalla con el resultado de la validación y detalles de la factura.

## Integración con la API de Factus

- La aplicación utiliza el endpoint `https://api-sandbox.factus.com.co/v1/bills/validate` para validar las facturas.
- Se requiere un token de autorización almacenado en `localStorage` bajo la clave `authToken`.
- Los datos se envían en formato JSON con la estructura esperada por la API, incluyendo información general, período de facturación, cliente, productos y retenciones.
- La respuesta de la API se procesa para mostrar información relevante como estado, mensaje, datos de la empresa, cliente, factura, productos y retenciones.

## Estructura del Formulario

- **Información General:** campos para rango de numeración, código de referencia, observaciones, forma y método de pago, fecha de vencimiento.
- **Período de Facturación:** fechas y horas de inicio y fin del período facturado.
- **Datos del Cliente:** identificación, DV, empresa, nombre comercial, nombres, dirección, email, teléfono, IDs legales y tributarios.
- **Productos/Servicios:** lista dinámica de productos o servicios con campos para código de referencia, nombre, cantidad, tasa de descuento, precio, tasa de impuesto, unidad de medida, código estándar, exclusión y tributo.
- **Retenciones:** para cada producto/servicio se pueden agregar múltiples retenciones con código y tasa.

## Requisitos

- Navegador web moderno con soporte para JavaScript.
- Token de autorización válido para la API de Factus almacenado en `localStorage` como `authToken`.

## Notas

- El sistema está diseñado para funcionar con la API sandbox de Factus para pruebas.
- Se recomienda validar que el token de autorización esté presente antes de usar el formulario.
- La interfaz es responsiva y amigable para facilitar la entrada de datos.

---

Desarrollado por Halltec para el reto de Factus.
