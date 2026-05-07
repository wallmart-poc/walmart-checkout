# walmart-checkout · Checkout Service

Order orchestration gRPC service. Coordinates the full checkout flow across cart, catalog, pricing, shipping, payment, and email confirmation.

## Stack
- **Language:** Go 1.21
- **Framework:** gRPC

## API
Implements `CheckoutService` from `demo.proto`:
- `PlaceOrder(PlaceOrderRequest) → PlaceOrderResponse`

## Running locally
```bash
go mod vendor
go run .
```
Service listens on port `5050` by default (`CHECKOUT_SERVICE_PORT`).

## Dependencies
All addresses are configured via environment variables:

| Env var | Service |
|---|---|
| `CART_SERVICE_ADDR` | walmart-cart |
| `PRODUCT_CATALOG_SERVICE_ADDR` | walmart-product-catalog |
| `CURRENCY_SERVICE_ADDR` | walmart-currency |
| `SHIPPING_SERVICE_ADDR` | walmart-shipping |
| `EMAIL_SERVICE_ADDR` | walmart-email |
| `PAYMENT_SERVICE_ADDR` | walmart-payments |

