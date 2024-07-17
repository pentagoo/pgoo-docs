---
sidebar_position: 2
---

# API

<code>POST</code> <code><b>https://api.pentagoo.com/api/payment/create</b></code> <code>(crea un nuevo pago)</code>

Este servicio debe ser invocado para generar un nuevo pago

##### Header

> | nombre            |  tipo     | tipo de datos      | descripcion                     |
> |-------------------|-----------|----------------|-------------------------------------|
> | `Content-Type`    |  required | string         | `application/json`                    |
> | `OAuth`           |  required | string         | `integrationKey:integrationSecret`    |

##### Parameters

> | nombre              |  tipo   | tipo de datos      | description                     |
> |-------------------|-----------|----------------|-------------------------------------|
> | `refId`           |  required | string         | orden       |
> | `description`     |  required | string         | orden       |
> | `amount`          |  required | string         | orden       |

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                |                                                                     |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |


<code>POST</code> <code><b>https://sitio_api_empresa/servicio</b></code> <code>(servicio de la empresa que se invocara al procesar un pago)</code>

Este servicio se debera implementar desde el lado de la compania, el cual pentagoo invocara luego de procesar un pago

##### Parameters

> | nombre            | tipo de datos  | description                     |
> |-------------------|----------------|---------------------------------|
> | `amount`          | string         | orden       |
> | `date`            | string         | orden       |
> | `blockchain`      | string         | orden       |
> | `hash`            | string         | orden       |
> | `paymentId`       | string         | orden       |
> | `orderId`         | string         | orden       |
