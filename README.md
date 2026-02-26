# 🏦 Bank API – TODO List z mikroserwisami (NestJS)

---

# 🔹 Mikroserwisy i ich opis

## 1️⃣ Auth Service

* Obsługa rejestracji i logowania (JWT + refresh tokens)
* Hashowanie haseł
* Rate limiting logowania
* Blokada konta po X nieudanych próbach
* Role-based access control (USER / ADMIN / SUPPORT)
* Custom decorator @CurrentUser

## 2️⃣ User Service

* Zarządzanie profilami użytkowników
* KYC (zweryfikowany / niezweryfikowany)
* Aktualizacja ról i statusów (ADMIN)
* Historia działań użytkownika (opcjonalnie)

## 3️⃣ Account Service

* Tworzenie i zarządzanie kontami bankowymi
* Obsługa wielu walut
* Sprawdzenie salda
* Aktywacja/dezaktywacja kont

## 4️⃣ Transaction Service

* Przelewy wewnętrzne i zewnętrzne (symulacja)
* Historia transakcji
* Harmonogramowane przelewy (cron)
* Obsługa transakcji w bazie + pessimistic locking
* Emitowanie eventów dla Audit i Notification Service

## 5️⃣ Card Service

* Tworzenie kart przypisanych do kont
* Blokada / odblokowanie kart
* Limity dzienne
* Symulacja płatności kartą

## 6️⃣ Audit / Notification Service

* Rejestrowanie wszystkich operacji finansowych
* Logi działań administratorów
* Powiadomienia dla użytkowników (opcjonalnie WebSocket / email)

## 7️⃣ API Gateway

* Punkt wejścia dla frontendu / mobile app
* Agregacja endpointów mikroserwisów
* Autoryzacja JWT
* Walidacja requestów

---

# ✅ 0. Project Setup

* [ ] Initialize NestJS project (monorepo lub Nx)
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

Zbudować działający Bank API jako system mikroserwisowy, pokazujący profesjonalną architekturę, bezpieczeństwo, skalowalność i logikę finansową.
