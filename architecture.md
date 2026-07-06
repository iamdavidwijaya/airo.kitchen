# Architecture

## System Shape

Airo Kitchen should be implemented as a modular monolith first, with clean module boundaries that can later become services if the chain grows beyond the first 100 branches.

## Applications

- `apps/web`: Next.js operations dashboard, POS, inventory, CRM, and BI
- `apps/kds`: dedicated kitchen display mode, optimized for tablets and monitors
- `apps/api`: NestJS REST API with Swagger documentation
- `packages/ui`: shared shadcn/ui components and Airo Kitchen theme tokens
- `packages/domain`: shared TypeScript domain types and validation schemas

## Backend Modules

- Auth and RBAC
- Organization and branch management
- POS orders, shifts, payments, refunds
- Kitchen display and station routing
- Inventory, warehouses, batches, expiry
- Recipes, costing, yield, margin
- Procurement and supplier performance
- CRM, loyalty, rewards, campaigns
- BI, reports, forecasting, notifications
- Audit logs and system activity

## Realtime

Socket.io channels:

- `branch:{branchId}:orders`
- `branch:{branchId}:kitchen`
- `branch:{branchId}:inventory`
- `org:{orgId}:alerts`

## Offline POS

Use IndexedDB in the POS client for offline order capture. Each offline order gets a client-generated UUID and sync status. The backend accepts idempotency keys to prevent duplicate orders after reconnection.

## Security

- Password hashing with Argon2 or bcrypt
- JWT access tokens and rotating refresh tokens
- RBAC permissions checked at controller and service boundaries
- Helmet, CORS allowlist, rate limiting, DTO validation
- Prisma parameterized queries
- Audit trail for sensitive changes
