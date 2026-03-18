# TEAM_PLAN.md

---

## 1. 👥 Team Roles (6 Developers)

*   **Developer 1:** Auth, Security & Logging  
*   **Developer 2:** Backend Core APIs & Deployment  
*   **Developer 3:** Database & Schema  
*   **Developer 4:** Frontend UI  
*   **Developer 5:** Search & Analytics  
*   **Developer 6:** Integration, API Contracts & Testing  

---

## 2. 📌 Task Assignment per Developer

### Developer 1: Auth, Security & Logging
*   **Assigned Tasks:**
    *   Implement JWT Authentication
    *   Implement Role-Based Access Control (RBAC)
    *   API Request Validation
    *   Rate Limiting
    *   Logging Setup (Morgan + Winston)
*   **Modules Owned:** `server/src/middleware/`, `auth.controller.js`
*   **Files Likely Modified:** `auth.js`, `validate.js`, `logger.js`
*   **Deliverables:**
    * Secure authentication system
    * Protected APIs
    * Standardized request validation
    * Logging and security layer

---

### Developer 2: Backend Core APIs & Deployment
*   **Assigned Tasks:**
    *   Unique Project ID Generation
    *   Project Continuity / Batch Shifting (Backend)
    *   File Storage Migration (AWS S3 / Cloud)
    *   Deployment Setup (Env config, hosting)
*   **Modules Owned:** Core project APIs
*   **Files Likely Modified:**
    * `project.core.controller.js` ✅ (separated)
    * `project.routes.js`
    * `upload.js`, `s3.js`
*   **Deliverables:**
    * Stable core APIs
    * File handling system
    * Deployment-ready backend

---

### Developer 3: Database & Schema
*   **Assigned Tasks:**
    *   Schema Update: PRN + Identity Enforcement
    *   Schema Update: Group Projects (1–3 members)
    *   Schema Update: Domain/Skill Tagging
    *   Database Indexing & Optimization
*   **Modules Owned:** `server/src/models/`
*   **Files Likely Modified:** `User.js`, `Project.js`
*   **Deliverables:**
    * Clean and scalable schema design
    * Optimized queries
    * Enforced constraints

---

### Developer 4: Frontend UI
*   **Assigned Tasks:**
    *   Remove Hardcoded Mock Data
    *   Centralized API Service Layer (Axios)
    *   Cross-Department Visibility UI
    *   Project Continuity UI
*   **Modules Owned:** `client/src/pages/`, `client/src/api/`
*   **Files Likely Modified:** dashboards, `axios.js`
*   **Deliverables:**
    * Clean UI connected to APIs
    * Modular components
    * No mock dependencies

---

### Developer 5: Search & Analytics
*   **Assigned Tasks:**
    *   Project Search & Filtering API
    *   Pagination & Query Optimization
    *   Industry Ranking System
    *   Plagiarism/Repetition Check
    *   Radar Chart Integration
*   **Modules Owned:**
    * `project.search.controller.js` ✅ (isolated)
    * analytics services
*   **Files Likely Modified:**
    * search controllers
    * chart components
*   **Deliverables:**
    * Efficient search APIs
    * Ranking system
    * Analytics features

---

### Developer 6: Integration, API Contracts & Testing
*   **Assigned Tasks:**
    *   Define API Response Contract (STANDARD)
    *   Integrate Dashboards with Live APIs
    *   End-to-End Testing
    *   Bug Tracking & Validation
*   **Modules Owned:**
    * API contract layer
    * integration layer
*   **Files Likely Modified:**
    * frontend integration files
    * test configs
*   **Deliverables:**
    * Stable frontend-backend integration
    * API consistency
    * tested workflows

---

## 3. 🔗 Dependency-Aware Execution

1. **Database Schema (Dev 3)** → MUST be completed first  
2. **Auth System (Dev 1)** → required before API protection  
3. **Core APIs (Dev 2)** → depends on schema  
4. **Search APIs (Dev 5)** → depends on tagging schema  
5. **Frontend UI (Dev 4)** → depends on API contracts  
6. **Integration (Dev 6)** → final step after APIs stabilize  

---

## 4. 🧱 Backend vs Frontend Strategy

* Backend (Dev 1, 2, 3) starts first
* API contract defined by Dev 6 early
* Frontend (Dev 4) builds UI using mock API structure
* Real integration only after API stabilization

---

## 5. 🔀 Conflict Prevention Strategy

### File Ownership Rules

| File | Owner |
|------|------|
| `auth/*` | Dev 1 |
| `models/*` | Dev 3 |
| `project.core.controller.js` | Dev 2 |
| `project.search.controller.js` | Dev 5 |
| `frontend pages` | Dev 4 |
| `integration/testing` | Dev 6 |

---

### Rules

- No editing another developer’s owned file without approval
- Use feature branches: `feature/devX-task`
- Break large files into modules
- Daily sync for shared dependencies

---

## 6. 📅 Parallel Execution Plan

### Phase 1 (Parallel Start)
- Dev 1 → Auth & Security
- Dev 3 → Schema updates
- Dev 4 → Remove mock data + UI cleanup
- Dev 6 → API contract + testing setup

---

### Phase 2 (Core Development)
- Dev 2 → Core APIs
- Dev 5 → Search & analytics
- Dev 4 → UI features

---

### Phase 3 (Integration & Finalization)
- Dev 6 → Full integration
- Dev 5 → Charts
- Dev 2 → Deployment
- Dev 1 → Final security checks

---

## 7. 🧪 Integration & Testing Ownership

**Owner: Developer 6**

Responsibilities:
- API contract enforcement
- End-to-end testing (Login → Upload → Approval)
- Bug tracking and validation
- Ensuring API/frontend consistency

---

## 8. ⚠️ Risk Areas

### Conflict Risks
- `project.routes.js`
- shared UI dashboards

### Bottlenecks
- Dev 3 (schema delays block all)
- Dev 1 (auth delays block security)
- Dev 6 (integration overload)

### Mitigation
- Strict module separation
- API contract defined early
- No schema changes after Phase 1

---

## 9. 🚀 Deployment Ownership

**Owner: Developer 2**

Responsibilities:
- Environment setup
- Backend deployment
- Database configuration
- File storage (S3/cloud)

---

## 10. 📌 Execution Rules

- Backend-first development
- No feature development before stabilization
- No direct push to `main`
- Mandatory PR reviews
- Code freeze before final integration

---
