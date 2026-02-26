# 🏦 Bank API – TODO List (NestJS)

---

# ✅ 0. Project Setup

* [x] Initialize NestJS project
* [ ] Configure ESLint + Prettier
* [ ] Setup environment variables (.env)
* [ ] Configure ConfigModule
* [ ] Setup Docker (app + PostgreSQL)
* [ ] Setup Docker Compose
* [ ] Configure Swagger
* [ ] Global validation pipe
* [ ] Global exception filter
* [ ] Logging interceptor
* [ ] Setup Jest + e2e tests

---

# ✅ 1. Database & Infrastructure

* [ ] Choose ORM (Prisma / TypeORM)
* [ ] Configure PostgreSQL connection
* [ ] Create migrations system
* [ ] Seed script
* [ ] Add DB transactions support
* [ ] Implement pessimistic locking (for transfers)

---

# ✅ 2. Core Entities (DB Models)

## Users

* [ ] id
* [ ] email (unique)
* [ ] password (hashed)
* [ ] role (USER / ADMIN / SUPPORT)
* [ ] isBlocked
* [ ] kycStatus
* [ ] failedLoginAttempts
* [ ] createdAt / updatedAt

## Accounts

* [ ] id
* [ ] userId (relation)
* [ ] currency
* [ ] balance
* [ ] isActive
* [ ] createdAt

## Transactions

* [ ] id
* [ ] fromAccountId
* [ ] toAccountId
* [ ] amount
* [ ] currency
* [ ] type (INTERNAL / EXTERNAL / CARD)
* [ ] status (PENDING / COMPLETED / FAILED)
* [ ] description
* [ ] createdAt

## Cards

* [ ] id
* [ ] accountId
* [ ] cardNumber (masked)
* [ ] expiryDate
* [ ] cvv (hashed)
* [ ] dailyLimit
* [ ] isBlocked

## AuditLogs

* [ ] id
* [ ] userId
* [ ] action
* [ ] entity
* [ ] entityId
* [ ] ipAddress
* [ ] metadata (JSON)
* [ ] createdAt

---

# ✅ 3. Authentication Module

* [ ] Register endpoint
* [ ] Login endpoint
* [ ] Hash passwords (bcrypt)
* [ ] JWT access token
* [ ] Refresh token
* [ ] Token rotation
* [ ] Logout
* [ ] Rate limiting on login
* [ ] Lock account after X failed attempts
* [ ] Role-based guard
* [ ] Custom @CurrentUser decorator

---

# ✅ 4. Users Module

* [ ] Get profile
* [ ] Update profile
* [ ] Block/unblock user (ADMIN)
* [ ] Change role (ADMIN)
* [ ] Verify KYC (ADMIN)

---

# ✅ 5. Accounts Module

* [ ] Create bank account
* [ ] Get user accounts
* [ ] Get account by id
* [ ] Deactivate account
* [ ] Balance endpoint

---

# ✅ 6. Transactions Module (CRITICAL)

## Internal Transfer

* [ ] Validate ownership
* [ ] Validate sufficient balance
* [ ] Start DB transaction
* [ ] Lock accounts (pessimistic lock)
* [ ] Decrease sender balance
* [ ] Increase receiver balance
* [ ] Create transaction record
* [ ] Commit transaction
* [ ] Rollback on error

## External Transfer (Simulation)

* [ ] Deduct funds
* [ ] Mark as PENDING
* [ ] Simulate async confirmation
* [ ] Update to COMPLETED

## Additional

* [ ] Transaction history (paginated)
* [ ] Filtering (date / type / status)
* [ ] Scheduled transfers (cron)

---

# ✅ 7. Cards Module

* [ ] Issue card
* [ ] Block/unblock card
* [ ] Set daily limit
* [ ] Simulate card payment
* [ ] Deduct funds with limit validation
* [ ] Decline if limit exceeded

---

# ✅ 8. Security Enhancements

* [ ] 2FA simulation (code verification)
* [ ] IP logging
* [ ] Rate limiting (global)
* [ ] Helmet
* [ ] CORS config
* [ ] Data masking in responses
* [ ] Prevent negative balances

---

# ✅ 9. Audit System

* [ ] Log every financial operation
* [ ] Log admin actions
* [ ] Middleware/interceptor for logging
* [ ] Audit query endpoint (ADMIN only)

---

# ✅ 10. Advanced Architecture (Optional – Senior Level)

* [ ] Implement CQRS pattern
* [ ] Separate Commands and Queries
* [ ] Domain events
* [ ] Event emitter for notifications
* [ ] Read/write separation
* [ ] Modular monolith structure

---

# ✅ 11. Testing

* [ ] Unit tests for services
* [ ] e2e tests for auth
* [ ] e2e tests for transfers
* [ ] Test transaction rollback
* [ ] Test edge cases (insufficient funds)
* [ ] Test concurrency case

---

# ✅ 12. DevOps & Deployment

* [ ] Production Dockerfile
* [ ] Health check endpoint
* [ ] CI pipeline (GitHub Actions)
* [ ] Deploy to VPS / Railway / Render
* [ ] Environment separation (dev/prod)

---

# ✅ 13. Bonus Features (Impressive Additions)

* [ ] Multi-currency accounts
* [ ] Currency conversion logic
* [ ] Freeze funds (authorization hold)
* [ ] Monthly statement generator
* [ ] PDF statement export
* [ ] WebSocket notifications
* [ ] Redis caching
* [ ] Admin dashboard API

---

# 🚀 Final Polish

* [ ] Clean README with architecture explanation
* [ ] ER diagram
* [ ] API documentation examples
* [ ] Postman collection
* [ ] Demo credentials
* [ ] Clear commit history

---

# 🏆 Goal

Build it like a real fintech backend – not a CRUD tutorial.
Focus on:

* Data consistency
* Security
* Architecture
* Edge cases
* Production readiness
