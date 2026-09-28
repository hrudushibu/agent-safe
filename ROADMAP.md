# Roadmap — Agent Safe

This document outlines the development plan for Agent Safe, an open-source security gateway for AI agents and MCP tools.

## 🎯 Vision

Build the most trusted security control plane for AI agents — making it safe to deploy autonomous AI in production environments where mistakes have consequences.

---

## Phase 1 — Foundation ✅ (Current)

**Goal**: Project scaffold and architecture planning

- [x] Next.js 16 + React 19 + TypeScript setup
- [x] shadcn/ui component library integration
- [x] App and console layout skeletons
- [x] Project documentation (README, LICENSE, SECURITY)
- [ ] Core data model design
- [ ] Architecture decision records (ADR)
- [ ] Technology selection (database, auth, etc.)

**Status**: Basic project structure complete. Architecture design in progress.

---

## Phase 2 — Core Data Models

**Goal**: Define foundational data structures

- [ ] Agent entity definition
- [ ] Tool catalog schema
- [ ] Policy model and DSL design
- [ ] Permission rule structure
- [ ] Audit log format
- [ ] Database schema (PostgreSQL/MongoDB/etc.)
- [ ] ORM/data access layer

---

## Phase 3 — Permission System

**Goal**: Basic tool access control

- [ ] Agent registration and management
- [ ] Tool metadata and catalog
- [ ] Simple allow/deny permissions
- [ ] Permission checking logic
- [ ] Permission API endpoints

---

## Phase 4 — Policy Engine Foundation

**Goal**: Rule-based access decisions

- [ ] Policy definition format (JSON/YAML)
- [ ] Policy evaluation engine
- [ ] Basic condition matching
- [ ] Policy storage and retrieval
- [ ] Policy testing framework

---

## Phase 5 — Audit Logging

**Goal**: Track all security decisions

- [ ] Structured audit log format
- [ ] Audit logger implementation
- [ ] Log storage and retention
- [ ] Basic audit log viewer UI
- [ ] Log search and filtering

---

## Phase 6 — UI Development

**Goal**: Build management interface

- [ ] Dashboard layout
- [ ] Agent management interface
- [ ] Tool permission configuration
- [ ] Policy editor (basic)
- [ ] Audit log viewer

---

## Phase 7 — Approval Workflows

**Goal**: Human-in-the-loop controls

- [ ] Approval request model
- [ ] Approval queue system
- [ ] Approval routing logic
- [ ] Approval UI
- [ ] Notification system

---

## Phase 8 — Risk Scoring

**Goal**: Automated risk assessment

- [ ] Risk scoring algorithm design
- [ ] Tool risk classification
- [ ] Context-based risk adjustment
- [ ] Risk dashboard

---

## Phase 9 — Integration & API

**Goal**: External system integration

- [ ] REST API for tool execution
- [ ] Webhook support
- [ ] MCP tool protocol support
- [ ] API documentation

---

## Phase 10 — Production Readiness

**Goal**: Deploy-ready system

- [ ] Authentication and authorization
- [ ] Multi-tenancy support
- [ ] Performance optimization
- [ ] Security audit
- [ ] Deployment guides
- [ ] CI/CD pipeline
- [ ] v1.0.0 release

---

## 💡 Future Considerations

- ML-based anomaly detection
- Advanced policy language
- Enterprise features (SSO, RBAC)
- Plugin system for custom policies
- SaaS deployment option

---

## 🤝 Get Involved

Interested in contributing? Check [CONTRIBUTING.md](./CONTRIBUTING.md) or reach out to [hrudushibu.tech@gmail.com](mailto:hrudushibu.tech@gmail.com).

---

**Last updated**: 2026-09-28  
**Current Phase**: Phase 1 (Foundation)
