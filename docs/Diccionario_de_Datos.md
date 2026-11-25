# Diccionario de Datos

## Proyecto

Predicción de incumplimiento de tarjetas de crédito utilizando el dataset **Default of Credit Card Clients (UCI)**.

## Descripción general

El conjunto de datos contiene información de 30.000 clientes de tarjetas de crédito de Taiwán e incluye variables demográficas, información crediticia, historial de pagos, estados de cuenta y montos abonados.

El objetivo es predecir si un cliente incumplirá el pago durante el mes siguiente.

---

# Variable objetivo

## default.payment.next.month

Indica si el cliente incumplió el pago durante el mes siguiente.

| Valor | Significado |
|---------|---------|
| 0 | No incumplió |
| 1 | Incumplió |

---

# Variables de identificación

## ID

Identificador único del cliente.

**Uso en el proyecto:** únicamente para identificación. No se utilizará para entrenar modelos.

---

# Variables demográficas

## LIMIT_BAL

Monto total del crédito otorgado al cliente (expresado en dólares taiwaneses NT$).

Incluye crédito individual y crédito familiar o complementario.

---

## SEX

Sexo del cliente.

| Valor | Significado |
|---------|---------|
| 1 | Masculino |
| 2 | Femenino |

---

## EDUCATION

Nivel educativo.

| Valor | Significado |
|---------|---------|
| 1 | Posgrado |
| 2 | Universidad |
| 3 | Secundario |
| 4 | Otros |
| 5 | Desconocido |
| 6 | Desconocido |

---

## MARRIAGE

Estado civil.

| Valor | Significado |
|---------|---------|
| 1 | Casado |
| 2 | Soltero |
| 3 | Otros |

---

## AGE

Edad del cliente expresada en años.

---

# Historial de pagos

Estas variables representan el estado de pago histórico del cliente.

## Escala de atraso

| Valor | Significado |
|---------|---------|
| -1 | Pago puntual |
| 1 | Retraso de 1 mes |
| 2 | Retraso de 2 meses |
| 3 | Retraso de 3 meses |
| 4 | Retraso de 4 meses |
| 5 | Retraso de 5 meses |
| 6 | Retraso de 6 meses |
| 7 | Retraso de 7 meses |
| 8 | Retraso de 8 meses |
| 9 | Retraso de 9 meses o más |

---

## PAY_0

Estado de pago en septiembre de 2005.

## PAY_2

Estado de pago en agosto de 2005.

## PAY_3

Estado de pago en julio de 2005.

## PAY_4

Estado de pago en junio de 2005.

## PAY_5

Estado de pago en mayo de 2005.

## PAY_6

Estado de pago en abril de 2005.

---

# Estados de cuenta

Representan el importe del estado de cuenta mensual en NT$.

## BILL_AMT1

Importe del estado de cuenta de septiembre de 2005.

## BILL_AMT2

Importe del estado de cuenta de agosto de 2005.

## BILL_AMT3

Importe del estado de cuenta de julio de 2005.

## BILL_AMT4

Importe del estado de cuenta de junio de 2005.

## BILL_AMT5

Importe del estado de cuenta de mayo de 2005.

## BILL_AMT6

Importe del estado de cuenta de abril de 2005.

---

# Pagos realizados

Representan los importes efectivamente abonados por el cliente.

## PAY_AMT1

Pago realizado en septiembre de 2005.

## PAY_AMT2

Pago realizado en agosto de 2005.

## PAY_AMT3

Pago realizado en julio de 2005.

## PAY_AMT4

Pago realizado en junio de 2005.

## PAY_AMT5

Pago realizado en mayo de 2005.

## PAY_AMT6

Pago realizado en abril de 2005.

---

# Agrupación funcional de variables

## Perfil del cliente

- SEX
- EDUCATION
- MARRIAGE
- AGE

## Capacidad crediticia

- LIMIT_BAL

## Comportamiento histórico de pago

- PAY_0
- PAY_2
- PAY_3
- PAY_4
- PAY_5
- PAY_6

## Estados de cuenta

- BILL_AMT1
- BILL_AMT2
- BILL_AMT3
- BILL_AMT4
- BILL_AMT5
- BILL_AMT6

## Pagos realizados

- PAY_AMT1
- PAY_AMT2
- PAY_AMT3
- PAY_AMT4
- PAY_AMT5
- PAY_AMT6

## Variable objetivo

- default.payment.next.month

---

# Objetivo de negocio

El objetivo del proyecto es identificar clientes con alta probabilidad de incumplimiento de pago durante el próximo período.

Las predicciones pueden utilizarse para:

- gestión de riesgo crediticio;
- revisión manual de solicitudes;
- definición de límites de crédito;
- estrategias de seguimiento preventivo;
- evaluación de cartera.

---

# Consideraciones para el modelado

- La variable objetivo presenta desbalance de clases.
- El falso negativo es potencialmente el error más costoso para el negocio, ya que implica clasificar como cliente confiable a un cliente que terminará incumpliendo.
- Variables relacionadas con el historial de pagos (PAY_0 a PAY_6) probablemente tendrán alta relevancia predictiva.
- Las variables BILL_AMT y PAY_AMT permiten describir el comportamiento financiero reciente del cliente.
- La variable ID no se utilizará durante el entrenamiento.
