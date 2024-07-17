---
sidebar_position: 2
---

# API

<code>POST</code> <code><b>https://api.pentagoo.com/api/payment/create</b></code> <code>(crea un nuevo pago)</code>

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
