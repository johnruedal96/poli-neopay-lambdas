# NeoPay Lambdas

Lambdas AWS para procesamiento de pagos asíncrono via SQS.

## Lambdas

- **Producer**: Recibe pagos via HTTP (API Gateway) y los encola en SQS
- **Consumer**: Lee mensajes de SQS y persite en PostgreSQL


### Probar Producer

```bash
curl -X POST "https://<api-id>.execute-api.us-east-1.amazonaws.com/pagos" \
  -H "Content-Type: application/json" \
  -d "{\"amount\": 10.50, \"currency\": \"USD\"}"
```

Respuesta esperada:
```json
{
  "message": "Pago recibido y encolado para procesamiento asíncrono",
  "paymentId": "PAY-001",
  "eventType": "PagoPendiente"
}
```
