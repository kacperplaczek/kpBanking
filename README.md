# 🏦 NodeBank Bank API – TODO List with Microservices (NestJS)

---

# 🔹 Microservices and their Description

## 1️⃣ Auth Service

* Handles registration and login (JWT + refresh tokens)
* Password hashing
* Login rate limiting
* Account lock after X failed attempts
* Role-based access control (USER / ADMIN / SUPPORT)
* Custom decorator @CurrentUser

## 2️⃣ User Service

* Manage user profiles
* KYC (verified / unverified)
* Update roles and statuses (ADMIN)
* Optional: user activity history

## 3️⃣ Account Service

* Create and manage bank accounts
* Multi-currency support
* Check balance
* Activate / deactivate accounts

## 4️⃣ Transaction Service

* Internal and external transfers (simulation)
* Transaction history
* Scheduled transfers (cron)
* DB transaction handling + pessimistic locking
* Emit events for Audit and Notification Service

## 5️⃣ Card Service

* Issue cards linked to accounts
* Block / unblock cards
* Daily limits
* Simulate card payments

## 6️⃣ Audit / Notification Service

* Log all financial operations
* Log admin actions
* User notifications (optional: WebSocket / email)

## 7️⃣ API Gateway

* Entry point for frontend / mobile app
* Aggregates endpoints from microservices
* JWT authorization
* Request validation

---

# ✅ 0. Project Setup

* [ ] Initialize NestJS project (monorepo or Nx)
* [ ] Configure ESLint + Prettier
* [ ] Setup environment variables (.env)
* [ ] Configure ConfigModule
* [ ] Setup Docker (app + PostgreSQL)
* [ ] Setup Docker Compose for all services
* [ ] Configure Swagger in API Gateway
* [ ] Global validation pipe
* [ ] Global exception filter
* [ ] Logging interceptor
* [ ] Setup Jest + e2e tests

---

# ✅ 1. Database & Infrastructure

* [ ] Choose ORM (Prisma / TypeORM) for each microservice
* [ ] Configure PostgreSQL connection
* [ ] Create migrations system
* [ ] Seed script
* [ ] Add DB transactions support
* [ ] Implement pessimistic locking (for transfers)

---

# ✅ 2. Core Entities (per service)

### Auth Service

* Users, roles, failedLoginAttempts, JWT

### User Service

* Profiles, KYC status, history logs

### Account Service

* Accounts, balance, currency, isActive

### Transaction Service

* Transactions, type, status, description

### Card Service

* Cards, limits, status

### Audit Service

* AuditLogs: userId, action, entity, entityId, ipAddress, metadata, createdAt

---

# ✅ 3. Authentication Module

* [ ] Register endpoint
* [ ] Login endpoint
* [ ] Hash passwords (bcrypt)
* [ ] JWT access token + refresh token
* [ ] Logout endpoint
* [ ] Role-based guard
* [ ] Rate limiting + account lock
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

# ✅ 6. Transactions Module

* [ ] Internal transfer: validate ownership, balance, DB transaction, locks, create record
* [ ] External transfer: simulate async confirmation
* [ ] Transaction history (paginated + filters)
* [ ] Scheduled transfers (cron)

---

# ✅ 7. Cards Module

* [ ] Issue card
* [ ] Block/unblock card
* [ ] Set daily limit
* [ ] Simulate card payment
* [ ] Decline if limit exceeded

---

# ✅ 8. Security Enhancements

* [ ] 2FA simulation
* [ ] IP logging
* [ ] Rate limiting
* [ ] Helmet
* [ ] CORS config
* [ ] Data masking
* [ ] Prevent negative balances

---

# ✅ 9. Audit System

* [ ] Log all financial operations
* [ ] Log admin actions
* [ ] Middleware/interceptor for logging
* [ ] Audit query endpoint (ADMIN only)

---

# ✅ 10. Advanced Architecture (Optional)

* [ ] Implement CQRS
* [ ] Separate Commands and Queries
* [ ] Domain events
* [ ] Event emitter for notifications
* [ ] Read/write separation
* [ ] Modular monolith or microservice structure

---

# ✅ 11. Testing

* [ ] Unit tests per service
* [ ] e2e tests for auth, accounts, transactions
* [ ] Test transaction rollback
* [ ] Test edge cases (insufficient funds, concurrency)

---

# ✅ 12. DevOps & Deployment

* [ ] Dockerfile per microservice
* [ ] Health check endpoint
* [ ] CI pipeline (GitHub Actions)
* [ ] Deploy to VPS / Railway / Render
* [ ] Environment separation (dev/prod)

---

# ✅ 13. Bonus Features

* [ ] Multi-currency accounts
* [ ] Currency conversion
* [ ] Freeze funds (authorization hold)
* [ ] Monthly statement generator + PDF export
* [ ] WebSocket notifications
* [ ] Redis caching
* [ ] Admin dashboard API

---

# 🚀 Final

* [ ] Clean README with architecture explanation
* [ ] ER diagram + microservices diagram
* [ ] API documentation examples
* [ ] Postman collection
* [ ] Demo credentials
* [ ] Clear commit history

---

# 🏆 Goal

Build a fully working Bank API as a microservice system, demonstrating professional architecture, security, scalability, and financial logic.
