---
sidebar_position: 2
---

# API

<code>POST</code> <code><b>https://api.pentagoo.com/api/payment/create</b></code> <code>(crea un nuevo pago)</code>

Este servicio debe ser invocado para generar un nuevo pago

##### Header

> | nombre            |  tipo     | tipo de datos      | descripción                     |
> |-------------------|-----------|----------------|-------------------------------------|
> | `Content-Type`    |  required | string         | `application/json`                    |
> | `OAuth`           |  required | string         | `integrationKey:integrationSecret`    |

##### Parameters

> | nombre              |  tipo   | tipo de datos      | descripción                     |
> |-------------------|-----------|----------------|-------------------------------------|
> | `refId`           |  required | string         | Un identificador único para la orden.                                       Este campo es utilizado para correlacionar el pago con un pedido específico en su sistema.|
> | `description`     |  required | string         | Una breve descripción del pago o la transacción. Esto puede incluir información relevante como el concepto del pago o detalles del servicio/producto.|
> | `amount`          |  required | string         | La cantidad total a pagar en la transacción. (por ejemplo, 100.00 USD).|

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                |                                                                     |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |


<code>POST</code> <code><b>https://sitio_api_empresa/servicio</b></code> <code>(servicio de la empresa que se invocara al procesar un pago)</code>

Este servicio se debera implementar desde el lado de la compania, el cual pentagoo invocara luego de procesar un pago

#### Parameters

| nombre      | tipo de datos | descripción                                                                                                                                                   |
|-------------|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `amount`    | string        | La cantidad total a pagar en la transacción. (por ejemplo, 100.00 USD).                                            |
| `date`      | string        | La fecha y hora en que se realiza la transacción. Debe estar en formato ISO 8601 (por ejemplo, 2024-07-17T12:34:56Z).|
| `blockchain`| string        | La red blockchain en la que se está procesando el pago (por ejemplo, Binance Smart Chain, Ethereum).|
| `hash`      | string        | El hash de la transacción en la blockchain. Este es un identificador único que se puede utilizar para verificar la transacción en la red blockchain correspondiente.|
| `paymentId` | string        | El identificador único del pago generado por Pentagoo. Este ID se utiliza para rastrear y gestionar la transacción dentro del sistema de Pentagoo.|
| `orderId`   | string        | El identificador único de la orden o transacción en su sistema. Este campo permite correlacionar el pago con una orden específica en su base de datos.|

