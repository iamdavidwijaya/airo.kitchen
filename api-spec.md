# REST API Map

Base path: `/api/v1`

## Auth

- `POST /auth/login`
- `POST /auth/refresh`
- `POST /auth/logout`
- `GET /auth/me`

## Branches

- `GET /branches`
- `POST /branches`
- `GET /branches/:id`
- `PATCH /branches/:id`

## POS

- `POST /shifts/open`
- `POST /shifts/:id/close`
- `GET /tables`
- `POST /orders`
- `GET /orders/:id`
- `PATCH /orders/:id`
- `POST /orders/:id/split`
- `POST /orders/:id/merge`
- `POST /orders/:id/payments`
- `POST /orders/:id/refunds`
- `GET /reports/sales`

## Kitchen Display

- `GET /kitchen/orders`
- `PATCH /kitchen/orders/:id/status`
- `GET /kitchen/analytics`

## Inventory

- `GET /inventory/items`
- `POST /inventory/stock-in`
- `POST /inventory/stock-out`
- `POST /inventory/transfers`
- `POST /inventory/adjustments`
- `GET /inventory/alerts`

## Recipes

- `GET /recipes`
- `POST /recipes`
- `PATCH /recipes/:id`
- `GET /recipes/:id/costing`

## Procurement

- `POST /purchase-requests`
- `POST /purchase-requests/:id/approve`
- `POST /purchase-orders`
- `POST /goods-receipts`
- `GET /suppliers/performance`

## CRM

- `GET /customers`
- `POST /customers`
- `GET /loyalty/members`
- `POST /loyalty/points`
- `POST /campaigns`

## BI and Forecasting

- `GET /bi/summary`
- `GET /bi/branch-comparison`
- `GET /forecast/sales`
- `GET /forecast/ingredients`
- `GET /forecast/purchase-recommendations`
