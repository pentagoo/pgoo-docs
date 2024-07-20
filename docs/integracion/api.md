---
sidebar_position: 2
---

# API

`POST` **`https://api.pentagoo.com/api/payment/create`** (Crear un nuevo pago)

Este endpoint se utiliza para generar un nuevo pago.

### Header

> | Nombre            | Tipo      | Tipo de Datos  | Descripción                                        |
> |-------------------|-----------|----------------|----------------------------------------------------|
> | `Content-Type`    | Requerido | String         | `application/json`                                 |
> | `OAuth`           | Requerido | String         | `integrationKey:integrationSecret`                 |

### Parámetros

> | Nombre            | Tipo      | Tipo de Datos  | Descripción                                                                               |
> |-------------------|-----------|----------------|-------------------------------------------------------------------------------------------|
> | `refId`           | Requerido | String         | Identificador único para la orden, usado para correlacionar el pago con un pedido específico en su sistema. |
> | `description`     | Requerido | String         | Breve descripción del pago o la transacción, incluyendo información relevante como el concepto del pago o detalles del producto/servicio. |
> | `amount`          | Requerido | String         | Monto total a pagar en la transacción (por ejemplo, 100.00 USD).                    |

### Respuestas

> | Código HTTP | Content-Type           | Respuesta                                                            |
> |-------------|------------------------|----------------------------------------------------------------------|
> | `200`       | `application/json`     | Pago creado exitosamente                                             |
> | `400`       | `application/json`     | `{"code":"400","message":"Bad Request"}`                             |

---

`POST` **`https://sitio_api_empresa/servicio`** (Servicio de la empresa invocado al procesar un pago)

Este endpoint debe ser implementado por parte del cliente y será invocado por Pentagoo luego de procesar un pago.

### Parámetros

> | Nombre      | Tipo de Datos | Descripción                                                                                                                                |
> |-------------|---------------|--------------------------------------------------------------------------------------------------------------------------------------------|
> | `amount`    | String        | Monto total a pagar en la transacción (por ejemplo, 100.00 USD).                                                                      |
> | `date`      | String        | Fecha y hora de la transacción en formato ISO 8601 (por ejemplo, 2024-07-17T12:34:56Z).                       |
> | `blockchain`| String        | Red blockchain donde se está procesando el pago (por ejemplo, Binance Smart Chain, Ethereum).                                        |
> | `hash`      | String        | Hash de la transacción en la blockchain, un identificador único para verificar la transacción en la red correspondiente. |
> | `paymentId` | String        | Identificador único del pago generado por Pentagoo, usado para rastrear y gestionar la transacción. |
> | `orderId`   | String        | Identificador único de la orden o transacción en su sistema, permitiendo correlacionar el pago con una orden específica en su base de datos. |

